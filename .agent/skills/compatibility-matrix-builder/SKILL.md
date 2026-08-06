---
name: compatibility-matrix-builder
description: Plans and executes cross-browser / cross-platform compatibility testing for a set of web screens using the BrowserStack MCP server, which drives real browsers on real operating systems and real mobile devices in BrowserStack's cloud (not local emulation). Use this skill when the user asks to "build a compatibility matrix", "run cross-browser testing", "test on real devices/browsers via BrowserStack", or provides a target URL plus a list of screens that need OS x Browser x Device coverage. Requires the BrowserStack MCP server to be configured with BROWSERSTACK_USERNAME and BROWSERSTACK_ACCESS_KEY.
---

# Compatibility Matrix Builder (BrowserStack MCP Edition)

A QA automation skill that plans a minimal-coverage OS x Browser x Device test matrix per
screen, then drives it end-to-end through the **BrowserStack MCP server** — which
provisions genuinely different browsers, operating systems, and real mobile devices in
BrowserStack's cloud. This is a real-device execution, not a local Chromium viewport
emulation, so results from this skill can be reported as genuine cross-platform coverage.

The skill still acts as a **disciplined test executor under human supervision**: it opens
sessions, navigates, captures evidence, and proposes Pass/Fail based on what it observed —
but the human reviewer remains responsible for confirming every verdict before it is
submitted as part of the assignment.

---

## 1. Required Inputs

| Input | Description | Example |
|---|---|---|
| `target_url` | Base URL of the application under test | `https://prod-dev.ems-fitus.cloud/` |
| `screens` | List of screens to test, each with the path/navigation steps to reach it | `Dashboard`, `A4 - Participants & Reviews (tab: Review Students)`, `A5 - Check-in` |
| `credentials` | Login info if required | `admin@gmail.com / Admin@123` |
| `coverage_requirement` | Minimum coverage rule | Default: at least 3 OS, 5 browsers, 3 device classes, each appearing at least once **per screen** |
| `student_id_overlay` | The `MSSV@...edu.vn` text required on every screenshot by the assignment | `23127104@student.hcmus.edu.vn` |
| `browserstack_budget` | Approximate trial minutes/sessions remaining, if known | e.g. "~60 minutes left on trial" |

### Step 1 — Confirm inputs and connectivity before spending any BrowserStack minutes

```
I'm about to run cross-platform testing via BrowserStack MCP with:
- Target URL: <target_url>
- Screens: <list>
- Login: <credentials summary>
- Coverage target: 3 OS x 5 browsers x 3 device classes, per screen
- Estimated BrowserStack sessions needed: <n> (see matrix plan below)

BrowserStack trial minutes are limited - each session opened here consumes
real quota. Please confirm you want to proceed with this plan before I open
any sessions.
```

Do not open a single BrowserStack session until the user confirms the plan.

---

## 2. Matrix Planning (before touching BrowserStack)

### 2.1. Generate the minimal-coverage matrix

For each screen, produce the smallest set of cells (OS + Browser + Device combinations)
that still satisfies: every required OS appears at least once, every required browser
appears at least once, every required device class appears at least once.

Default coverage set (unless the user specifies otherwise):
- OS: Windows, macOS, Android, iOS
- Browsers: Chrome, Firefox, Safari, Edge, Samsung Internet (mobile) or Opera
- Device classes: Desktop, Tablet, Phone

Example plan for one screen (present this table to the user before execution):

| Cell | OS | Browser | Device |
|---|---|---|---|
| 1 | Windows | Chrome | Desktop |
| 2 | Windows | Firefox | Desktop |
| 3 | macOS | Safari | Desktop |
| 4 | macOS | Edge | Desktop |
| 5 | Android | Chrome | Phone (real device) |
| 6 | Android | Samsung Internet | Tablet (real device) |
| 7 | iOS | Safari | Phone (real device) |

Multiply by the number of screens to get the total planned BrowserStack sessions
(e.g. 7 cells x 3 screens = 21 sessions). Report this total to the user as part of the
confirmation step above, since it directly maps to trial-minute consumption.

### 2.2. Order cells to minimize session switching cost

Group cells by OS/device combination across all screens where possible (e.g. run all
three screens back-to-back within one BrowserStack Live session on Windows/Chrome before
switching to the next OS/Browser combination), rather than reopening a new session per
screen per cell. This reduces the number of separate session launches and conserves
trial minutes.

---

## 3. Execution via BrowserStack MCP

### 3.1. Per-cell workflow

For each planned cell, in the grouped order from 2.2:

1. **Launch a BrowserStack Live session** via the MCP tool, specifying the exact OS
   version, browser + version, and device (for mobile: a real device model, e.g.
   "Samsung Galaxy S24" or "iPhone 15", not a generic simulator entry).
2. **Navigate** to `target_url`.
3. **Authenticate** if `credentials` are provided. Verify login succeeded before
   proceeding (see failure handling, Section 3.3).
4. **Navigate** to the specific screen path/tab.
5. **Wait for the page to fully render** (network idle + a short buffer, since real
   mobile devices over BrowserStack's cloud may have different load timing than local
   testing).
6. **Capture a screenshot** through the MCP session.
7. **Overlay `student_id_overlay`** on the captured image before saving (top-right
   corner by default, consistent across all screenshots).
8. **Inspect the screenshot and, where the MCP tool provides it, session
   accessibility/DOM data** for:
   - Layout overflow, unwanted horizontal scroll
   - Overlapping elements
   - Truncated or clipped text
   - Interactive elements that appear too small to reliably tap (mobile cells)
   - Elements missing entirely compared to the desktop baseline
9. **Record a provisional Pass/Fail** with a factual note of what was observed. Label
   it clearly as "automated observation - pending human confirmation."
10. **End the session** promptly after capture to conserve trial minutes — do not leave
    BrowserStack sessions idle.

### 3.2. What NOT to do

- Do not batch multiple unrelated screens into a single ambiguous session log — capture
  and label each screen's evidence separately, even within the same browser session.
- Do not perform destructive actions (e.g. bulk Approve/Reject on A4, Delete) while
  running cross-platform checks unless the user has explicitly asked for functional
  verification on that platform, not just layout verification. Default to read-only
  navigation for this skill's purpose.
- Do not exceed the planned cell count without checking back with the user first -
  trial minutes are a real, exhaustible resource.

### 3.3. Failure handling

| Failure | Detection | Action |
|---|---|---|
| BrowserStack session fails to launch (queue timeout, device unavailable) | MCP tool returns an error or session never reaches "active" state | Retry once with an equivalent alternative device/browser version if available. If still failing, mark the cell "BLOCKED - BrowserStack session unavailable" and move to the next cell; do not silently skip without reporting it. |
| Site unreachable from BrowserStack's network | Navigation fails or times out inside the session | Distinguish this from a genuine app bug: note "environment/network issue during BrowserStack session," not a rendering Fail. |
| Login fails within the session | Login form still visible after submission, or error message shown | Do not retry more than twice per session (avoid lockouts). Report the exact error and stop for user input before continuing to other cells. |
| Screenshot capture fails | MCP tool returns no image or an error | Retry once. If it persists, log the cell as "evidence not captured" rather than fabricating a result. |
| Trial minutes run out mid-plan | MCP tool reports quota/session limit reached | Stop immediately, report exactly which cells were completed and which remain, and let the user decide whether to continue with a different account/tool or resume later. |

---

## 4. Output Files

Produce `<scenario>-compatibility-matrix.md`, matching the shared `06_cross_platform_matrix.md`
template (one sub-table per screen), with these additional columns:

```markdown
## Screen: <screen name>

| Cell | OS | Browser | Device | Pass/Fail | Notes | Screenshot | BrowserStack session evidence |
|---|---|---|---|---|---|---|---|
| 1 | Windows | Chrome | Desktop | Pass | | cp_A4_windows_chrome_desktop.png | session id / timestamp |
| 5 | Android | Chrome | Phone | Fail | "Approve All" button extends beyond right edge of screen, partially off-viewport | cp_A4_android_chrome_phone.png | session id / timestamp |
```

Screenshots saved as `cp_<screen>_<os>_<browser>_<device>.png` in a `screenshots/`
folder, each already carrying the student-ID overlay, sourced from an actual
BrowserStack session (never fabricated or substituted with a local emulation).

For any cell marked Fail, generate a bug-report entry using the same structure as the
`gui-checklist-executor` skill (steps to reproduce, expected, actual, severity),
referencing the exact OS/Browser/Device combination and, where available, the
BrowserStack session ID for traceability.

### Defect-type to severity guidance

| Defect type | Typical severity |
|---|---|
| Horizontal overflow / unwanted scrollbar | 1-2 (Minor-Moderate) |
| Overlapping interactive elements | 2-3 (Moderate-Major) |
| Text truncation hiding meaningful content | 1-2 |
| Non-responsive control (unreliable tap target on real device) | 2 |
| Screen fully unusable on this real device/browser | 4 (Critical) |

---

## 5. End-of-Session Summary

```markdown
## Compatibility Matrix Run Summary - <scenario>

**Screens tested:** <list>
**BrowserStack sessions used:** <n> / planned <n>
**Coverage check (per screen):**

| Screen | OS covered | Browsers covered | Device classes covered | Complete? |
|---|---|---|---|---|
| ... | | | | Yes/No |

**Failures found (<count>), sorted by severity:**

| Severity | Screen | Cell | Short description |
|---|---|---|---|
| ... | | | |

**Cells not completed (if any):** <list + reason - blocked session, quota exhausted, etc.>
```

---

## 6. Guardrails (Non-negotiable)

- Never report a Pass/Fail for a cell that was not actually executed inside a real
  BrowserStack session in this run. Do not substitute a local Chromium approximation
  and label it as the target browser/OS/device.
- Never fabricate a BrowserStack session ID, screenshot, or result. If a session could
  not be completed (quota, failure, timeout), report it as incomplete - do not invent
  evidence to fill a gap in the matrix.
- Never skip the input/plan confirmation step (Section 1) before consuming BrowserStack
  minutes - trial quota is a real, shared, exhaustible resource for this assignment.
- Never perform destructive actions on the application under test during a
  cross-platform run without explicit user confirmation.
- Always apply the student-ID overlay before considering a screenshot "final" for
  submission - this is a hard requirement of the assignment's anti-cheat policy.
- If an observed layout issue is ambiguous (e.g. unclear whether spacing is a genuine
  defect or intentional design), mark it for human visual review rather than forcing
  a Pass or Fail verdict.
- Any suggested fix or root-cause explanation produced by BrowserStack's AI features
  must be presented to the user as a proposal only - never applied or treated as final
  without explicit human confirmation, consistent with the assignment's "human review"
  requirement.