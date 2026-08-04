---
name: gui-checklist-executor
description: Runs a structured GUI/usability checklist against a live web application using the Playwright MCP browser automation tools, screen by screen, and produces a filled-in checklist report with bug reports and failure screenshots. Use this skill whenever the user asks to "run the GUI checklist", "execute the checklist on [screen]", "test these screens against the checklist", or provides a target URL plus a list of screens to be checked against a shared reference checklist file (e.g. `share-gui-checklist.md`). Also trigger when the user asks to automate GUI/usability QA testing with Playwright.
---

# GUI Checklist Executor

A QA automation skill that drives a real browser (via Playwright MCP) through a list of
target screens, evaluates each item of a shared GUI checklist against what is actually
rendered/behaving on the page, and produces a fully documented, evidence-backed report.

This skill acts as a **disciplined test executor**, not a black box. Every Pass/Fail
verdict must be backed by a concrete observation (DOM state, screenshot, console log,
network response, or an explicit textual description of what was seen) — never a guess.

---

## 1. Required Inputs

Before any browser action is taken, the agent MUST collect the following three inputs.
If any of them is missing or ambiguous, STOP and ask the user — do not assume defaults
for the target URL, screen list, or credentials.

| Input | Description | Example |
|---|---|---|
| `target_url` | Base URL of the web application under test | `https://prod-dev.ems-fitus.cloud/` |
| `screens` | Ordered list of screens to test. Each screen needs: a name/ID, the path or navigation steps to reach it, and (optionally) any sub-tabs that belong to it | `A4 - Participants & Reviews (tabs: Registrants, Review Lecturers, Review Students)` |
| `credentials` | Login required? If yes: username/email + password. If the screen is public (no login), state that explicitly | `admin@gmail.com / Admin@123` |
| `reference_checklist` | Path to the shared checklist file to execute against | `share-gui-checklist.md` |

### Step 1 — Confirm inputs with the user

Before starting, restate the collected inputs back to the user in a short summary table
and ask for explicit confirmation. Do not proceed to browser automation until confirmed.

Template to use:

```
I'm about to run the GUI checklist with the following setup:
- Target URL: <target_url>
- Screens to test (in order): <list>
- Login: <credentials summary, or "no login required">
- Reference checklist: <reference_checklist>

Shall I proceed? (yes / adjust something first)
```

If the user says "yes", proceed to Step 2. If they want to adjust anything, update and
re-confirm before touching the browser.

---

## 2. Environment / Pre-flight Check

Before executing any checklist item, verify the environment is actually testable.
Never silently skip this step — a checklist run against a broken environment produces
worthless results and wastes the human reviewer's time.

### 2.1. Reachability check

1. Navigate to `target_url` using Playwright MCP.
2. Wait for network idle (or a maximum of 15 seconds).
3. Check the HTTP response status and page state.

### 2.2. Common failure modes and how to handle them

| Failure | Detection | Action |
|---|---|---|
| **Site down / DNS failure** | Navigation throws a connection error, or response status >= 500 | Stop immediately. Report to the user: "Target site appears unreachable ([error detail]). Please verify the URL / VPN / tunnel (e.g. ngrok) is active before re-running." Do NOT retry silently more than once. |
| **Timeout on page load** | No network-idle state reached within 15s, or explicit navigation timeout from Playwright | Retry once with an extended timeout (30s). If it fails again, log it as an environment issue (not a checklist Fail) and stop, asking the user to confirm the app is not undergoing a slow cold-start. |
| **Login failure** | After submitting credentials, the app still shows the login form, or an error toast/message appears | Do NOT retry credentials more than twice (avoid triggering account lockouts). Report the exact error message shown by the app and stop for user input. |
| **Element not found (selector mismatch)** | Playwright `locator` times out waiting for an expected element | Do not report this instantly as a UI bug. First take a full-page screenshot and a DOM/accessibility-tree snapshot for inspection. Retry the action once after a short wait (in case of async loading). If still not found, mark the specific checklist item as `Fail` with note "Expected element not found — see screenshot", not as an environment failure. |
| **Unexpected redirect / session expired mid-run** | Current URL no longer matches expected screen path | Pause the run, attempt one re-login, then resume from the screen that was interrupted. Log this event in the run notes regardless of outcome. |
| **Data required for a screen is missing** (e.g. no pending registrations to test Approve/Reject flow) | Screen loads correctly but shows an empty state where test data was expected | Do not fabricate data or force a false Pass/Fail. Mark the relevant item(s) as `NA` with note "No test data available at run time — requires manual seeding of [specific data]." |

### 2.3. Environment check summary

After the pre-flight check, report a short status to the user before proceeding to the
main checklist run:

```
Environment check: OK - site reachable, login successful, target screens accessible.
```
or
```
Environment check: BLOCKED - [reason]. Cannot proceed with checklist execution.
```

Only continue to Section 3 if the status is OK.

---

## 3. Checklist Execution Workflow

### 3.1. Load the reference checklist

Read `share-gui-checklist.md` fully before starting. This file defines the checklist
items, their IDs, IA category (IA-01 General UI, IA-02 Forms, IA-03 Navigation,
IA-04 Feedback/State), and heuristic reference. **Do not paraphrase or reformat these
items** — the output must preserve the exact item ID and wording from the reference file
so results can be cross-checked against the shared checklist.

### 3.2. Per-screen execution loop

For each screen in `screens` (in the given order):

1. **Navigate** to the screen (following the path/steps provided in the input). If the
   screen has sub-tabs, iterate through each sub-tab as a nested unit — do not skip any.
2. **Capture a baseline screenshot** of the screen in its default state, before any
   interaction. Save temporarily (not yet the final filename — see Section 4).
3. **For each checklist item applicable to this screen:**
   a. Determine if the item is testable through browser automation alone (e.g. DOM
      structure, element presence, color/style values, navigation behavior, response to
      clicks) or requires a judgment call that should be flagged for human review
      (e.g. subjective aesthetic quality, cross-device responsiveness beyond what the
      current run covers).
   b. Perform the minimal set of actions needed to observe the behavior described by the
      item (e.g. click a button and observe whether a confirmation dialog appears; type
      invalid input and observe whether a validation error is shown; toggle a filter and
      observe whether the URL updates).
   c. Record the verdict: `Pass`, `Fail`, or `NA` (not applicable to this screen).
   d. **Never guess.** If an item cannot be verified through available automation actions
      (e.g. "color contrast meets WCAG" without a contrast-checking tool, or "feels fast"),
      mark it `NA` with a note explaining what a human tester should verify manually.
   e. If the item fails, immediately capture a targeted screenshot showing the failure
      state (see Section 4 for naming convention).
4. **Do not modify persistent data unless the item explicitly requires it**, and only
   after confirming with the user for destructive actions (e.g. Delete, Reject All,
   Block user). Prefer read-only verification wherever the checklist item allows it.
5. **Log timing information** for items related to feedback/state (e.g. how long a toast
   remained visible, how long a spinner was shown) — this is required for IA-04 items.

### 3.3. Interaction principles (best practices)

- **Wait for stability, not fixed delays.** Prefer waiting for specific conditions
  (element visible, network idle, text present) over arbitrary `sleep()` calls, but allow
  a bounded timeout (e.g. 5-10s) before concluding an expected element/behavior is absent.
- **One assertion per action.** Don't chain multiple unrelated checklist items into a
  single interaction sequence — this makes failures hard to attribute to a specific item.
- **Isolate side effects.** If a test action changes system state (e.g. approving a
  registration), note this clearly in the report so the human reviewer knows the
  environment was mutated during the run.
- **Prefer accessibility-tree/DOM inspection over pixel comparison** for structural
  checks (e.g. presence of a label, disabled state of a button), and reserve visual
  screenshots for items that are inherently visual (layout, color, spacing).
- **Respect rate limits and avoid destructive loops.** Never repeat an action (e.g.
  double-submit tests) more than the minimum needed to observe the behavior.

---

## 4. Output: Files and Naming Conventions

### 4.1. Checklist result file

Produce one file: `<scenario>-gui-checklist.md`, where `<scenario>` is derived from the
scenario/screen set under test (e.g. `scenarioA-gui-checklist.md`).

This file MUST preserve the same table structure as `share-gui-checklist.md`
(same item IDs, same IA grouping), with these columns added per screen tested:

```markdown
## Screen: <screen name/ID> <(sub-tab, if applicable)>

| ID | IA | Checklist Item | Reference | Pass/Fail/NA | Notes | Screenshot |
|---|---|---|---|---|---|---|
| IA-04-03 | Feedback | Confirmation dialog appears before destructive bulk actions | Nielsen #5 | Fail | Clicked "Reject All" with no items selected - no dialog appeared, no toast, no visible reaction | screenshots/A4-bug-IA-04-03.png |
```

### 4.2. Screenshot naming convention

For every `Fail` item, save a screenshot using this exact pattern:

```
<screen>-bug-<itemID>.png
```

Examples:
- `A4-bug-IA-04-03.png`
- `A5-bug-IA-01-07.png`
- `Dashboard-bug-IA-01-06.png`

Store all screenshots in a `screenshots/` subfolder next to the checklist result file.
If a screen has multiple sub-tabs, prefix accordingly, e.g. `A4-ReviewStudents-bug-IA-04-07.png`.

Do not screenshot `Pass` or `NA` items unless the user explicitly requests full evidence
coverage — this keeps the output focused and avoids clutter.

---

## 5. Bug Report Writing

For every item marked `Fail`, generate a standalone bug report entry (in addition to its
row in the checklist table) using this exact structure:

```markdown
### BUG-<sequential number> - <short title>

- **Screen:** <screen/sub-tab>
- **Checklist item:** <item ID> - <item text>
- **Steps to reproduce:**
  1. <step>
  2. <step>
  3. <step>
- **Expected result:** <what the checklist item says should happen>
- **Actual result:** <what was actually observed, described factually, no speculation>
- **Severity:** <0 Cosmetic | 1 Minor | 2 Moderate | 3 Major | 4 Critical> - <one-line justification>
- **Screenshot:** screenshots/<screen>-bug-<itemID>.png
```

### Severity guidance (assign the lowest severity that honestly fits; do not inflate)

| Severity | When to use |
|---|---|
| 0 - Cosmetic | Purely visual inconsistency with no functional impact (e.g. inconsistent spacing) |
| 1 - Minor | Small usability friction, workaround available, no data risk |
| 2 - Moderate | Noticeable usability problem or missing feedback that could confuse users |
| 3 - Major | Broken core functionality on this screen, or a bulk/irreversible action with no confirmation safeguard |
| 4 - Critical | Data loss, security/privacy exposure, or the screen is unusable |

**Do not let the agent silently decide severity for ambiguous cases** — if a failure could
plausibly be Moderate or Major depending on business context the agent cannot know
(e.g. how often this action is used in production), state both possibilities and default
to the lower one, flagging it for human confirmation in the Notes column.

---

## 6. End-of-Session Summary

After all screens have been processed, output a concise summary directly in the
conversation (not just in the file) using this format:

```markdown
## Checklist Run Summary - <scenario>

**Screens tested:** <list>
**Environment status:** OK (see pre-flight check)
**Total items evaluated:** <N>
- Pass: <n>
- Fail: <n>
- NA: <n>

### Failures found (<count>), sorted by severity:

| Severity | ID | Screen | Short description |
|---|---|---|---|
| 4 | ... | ... | ... |
| 3 | ... | ... | ... |
| ... | | | |

Full details: see `<scenario>-gui-checklist.md` and `screenshots/`.

**Items requiring manual/human verification (marked NA):**
- <item> - <reason automation couldn't verify it>
```

Keep this summary short — it is a pointer to the full report, not a duplicate of it.
Do not editorialize about UI quality beyond what was literally observed.

---

## 7. Guardrails (Non-negotiable)

- Never fabricate a Pass/Fail verdict without having actually driven the browser to
  observe that state in this run.
- Never perform destructive/irreversible actions (Delete, Reject All, Block, Reset
  Password) without explicit user confirmation beforehand, even if a checklist item
  technically requires triggering that action to verify it.
- Never invent test data (fake users, fake events) to force a screen into a testable
  state — flag it as `NA` and ask the user to seed the required data instead.
- Never skip the input confirmation step (Section 1) or the environment check (Section 2),
  even if the user seems to be in a hurry.
- If the agent is uncertain whether an observed behavior constitutes a genuine failure
  of a specific checklist item versus simply not matching the item's wording, prefer
  under-reporting with a clear `NA` + explanation over forcing a Fail that could mislead
  the human reviewer.