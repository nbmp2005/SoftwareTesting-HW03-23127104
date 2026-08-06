# HW03-AI (EMS edition) — GUI & Usability Testing on EMS

**Họ tên:** Nguyễn Bình Minh Phương
**MSSV:** 23127104
**Scenario đã chọn:** Scenario A — Admin creates and manages events
---

## 1. Test Summary

| Hạng mục | Kết quả |
|---|---|
| **Scenario** | A — Admin manages events |
| **Screens tested (3)** | (A4) Participants & Reviews approval · (A5) Check-in tab · Admin Dashboard (KPIs) — screen tự chọn thêm trong Pool A |
| **Checklist item được thiết kế (group, > 40 yêu cầu)** | 50 items — IA-01: 12 · IA-02: 12 · IA-03: 12 · IA-04: 14 |
| **Checklist item được thực thi** | 150 lượt (50 item × 3 screen) |
| **Kết quả thực thi** | Pass: 56 · Fail: 12 · N/A: 82 → % Pass trên item áp dụng được: 82.4% (56/68) |
| **Số bug/finding phát hiện** | 28 tổng (17 Bug + 11 Usability) |
| **Phân bố theo Severity** | 0-Cosmetic: 0 · 1-Minor: 3 · 2-Moderate: 12 · 3-Major: 11 · 4-Critical: 2 |
| **Số người dùng thật tham gia Task 2** | 5 chính thức (P1–P5) + 1 pilot |
| **Task success rate (Task 2)** | 4/5 Completed, 1/5 Partial (80%) |
| **Điểm SUS trung bình (Task 2)** | 53.5/100 (min 35.0 – P5, max 75.0 – P3) — dưới benchmark ngành ~68/100 |
| **Compatibility cells covered (Task 3)** | 15 cells (3 screen × 5 cấu hình) → 10 Pass / 5 Fail |
| **Coverage Task 3** | 4 OS (Windows, macOS, Android, iOS) · 5 Browser (Chrome, Firefox, Edge, Samsung Internet, Safari) · 3 Device class (Desktop, Tablet, Phone) |
| **Demo video Agent Skill(s)** |
[Video agent skill GuiChecklist](https://youtu.be/g8B4ZIdky2g)
[Video agent skill CrossPlatformMatrix](https://youtu.be/fRcJO5lOgqU)

**Nhận định nổi bật (chi tiết ở Mục 5, `MainReport.md`):**
- Lỗi **responsive/layout** (IA-01-07) Fail đồng loạt trên cả 3/3 screen ở Task 1B, được xác nhận độc lập bởi Task 3 (iOS Safari Phone fail 3/3 screen, Android Tablet fail 2/3 screen) → cùng một root cause ở tầng layout dùng chung.
- 2 finding **Severity 4 (Critical)** chỉ được phát hiện qua Task 2 (usability testing với người dùng thật): không tìm được nơi nhập "Member code" để check-in, và không tìm được nơi duyệt đăng ký Pending — cả hai đều Pass tuyệt đối trên checklist tĩnh, cho thấy giá trị bổ trợ không thể thay thế của việc quan sát người dùng thật.

---

## 2. Bảng tự đánh giá (Self-Assessment)

| No. | Criteria | Grade (tối đa) | Self-Assessed Grade |
|---|---|---|---|
| 1a | Task 1A — Shared checklist (> 40 items, IA-01…IA-04) + reference sources + AI prompts (group) | 15 | 15 |
| 1b | Task 1B — Checklist execution ≥ 3 screens + bug reports (individual) | 15 | 15 |
| 2 | Task 2 — User testing với 5 người dùng thật (scenario + 5 session + phân tích → Usability Report) | 25 | 25 |
| 3 | Task 3 — Cross-Browser / Cross-Platform matrix (3 OS × 5 browser × 3 device class) | 25 | 25 |
| 4 | Bug & Usability Findings submission (Google Form) + aggregated log | 10 | 10 |
| 5 | Agent Skills | 10 | 10 |
| | **Total** | **100** | 100 |

---

## 3. Cấu trúc thư mục nộp bài

```
23127104_HW03_AI_GUIUsability_EMS_<Grade>/
├── README.md                      # file này — tổng quan + tự đánh giá
├── MainReport.md                  # báo cáo chính: scenario, checklist execution,
│                                   #   usability report, cross-platform report (Mục 1–10)
├── ChecklistExecution.md          # Task 1B — chi tiết 50 item checklist × 3 screen (150 dòng)
├── UserTestingEvidence.md         # Task 2 — kịch bản, 5 người tham gia (đã che thông tin),
│                                   #   ghi chú quan sát từng session, SUS/UEQ-S, metrics
├── CrossPlatformMatrix.md         # Task 3 — ma trận 15 cell (3 screen × 5 cấu hình OS/Browser/Device)
├── BugUsabilityFindingsLog.md     # Tổng hợp 28 finding (§7), khớp với Google Form
├── GroupChecklist/                # [Nhóm] Checklist gốc > 40 item, nguồn tham khảo, AI prompts
├── AI_Audit_report.md             # 
├── AI_critique.md                 # 
├── GitCommitLog.md                #
├── AgentSkillDemo.md              # 
└── images/
    ├── bugs/                      # screenshot cho các item Fail của Task 1B
    ├── usability_bug/             # screenshot cho các finding Task 2
    └── cross_platform/            # screenshot 15 cell Task 3 (overlay MSSV@...edu.vn)
```

