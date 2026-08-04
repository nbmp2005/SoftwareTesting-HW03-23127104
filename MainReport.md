# HW03 — Main Report
## GUI & Usability Testing on EMS

**Họ tên:** Nguyễn Bình Minh Phương     
**MSSV:** 23127104     

---

## 1. Scenario & Screens

### 1.1. Scenario đã chọn
Scenario A — Admin manages events.

### 1.2. Danh sách screens đã chọn và lý do

| # | Screen | Mô tả ngắn | Lý do chọn |
|---|---|---|---|
| 1 | (A4) Participants & Reviews approval | Bao gồm 3 tab con trong cùng 1 trang chi tiết sự kiện: Registrants (danh sách người tham gia nói chung), Review Lecturers (duyệt riêng cho giảng viên), Review Students (duyệt riêng cho sinh viên). Cả 3 tab dùng chung layout bảng, bộ lọc Status, và nút Export. | Đây là screen được đề bài gợi ý trực tiếp (A4). Được chọn vì có độ phức tạp UI cao nhất trong Pool A: (1) 6 màu trạng thái đòi hỏi tính nhất quán và khả năng phân biệt rõ ràng (IA-04), dễ gây nhầm lẫn nếu không có chú thích; (2) có ràng buộc nghiệp vụ đặc thù — nếu một giảng viên đăng ký nhiều vai trò trong cùng một lượt đăng ký, admin bắt buộc phải duyệt/từ chối HẾT tất cả vai trò rồi mới được bấm Apply, đây là logic dễ phát sinh lỗi validate; (3) progress bar và Export là các thành phần feedback/state giàu tiềm năng phát hiện bug. Tổng hợp lại, đây là screen có xác suất cao nhất để tìm ra bug thật và vấn đề usability đáng phân tích. |
| 2 | (A5) Check-in tab | Màn hình admin dùng để quét mã QR/barcode của người tham dự khi đến sự kiện, xử lý 4 trạng thái quét khác nhau (SUCCESS, ALREADY_CHECKED_IN, OUTSIDE_CHECKIN_WINDOW, PENDING_REVIEW — cần Accept/Decline), có nhật ký quét (log) cập nhật real-time và chức năng xuất Excel lịch sử quét. | Được đề bài gợi ý trực tiếp (A5). Được chọn vì đây là screen có nhiều trạng thái hệ thống (system status) nhất trong toàn bộ Pool A — rất phù hợp để kiểm thử IA-04 (feedback/state) và đánh giá mức độ tin cậy (trust) của người dùng vào kết quả hệ thống hiển thị. Yêu cầu real-time update của log cũng là điểm dễ phát sinh lỗi đồng bộ dữ liệu, một dạng bug phổ biến nhưng khó phát hiện nếu chỉ dùng checklist UI tổng quát. |
| 3 | Screen tự chọn — Admin Dashboard (KPIs) | Trang đầu tiên admin nhìn thấy sau khi đăng nhập, hiển thị 4 chỉ số tổng quan: Total Events, Total Check-ins, Attendance Rate, Total Users. | Mặc dù không nằm trong 5 screen gợi ý cụ thể (A1-A5) của mục 5, Dashboard được liệt kê chính thức là một phần của Pool A trong mục 4 của đề bài ("Dashboard KPIs (Total Events, Total Check-ins, Attendance Rate, Total Users)"), nên vẫn thuộc đúng function group "quản trị sự kiện". Việc chọn thêm screen này được đề bài cho phép ở mục 5 ("you may choose others in the same group, but you must justify the choice"). Lý do chọn cụ thể: (1) Dashboard tạo thành một luồng logic hoàn chỉnh cùng A4 và A5 — Dashboard (giám sát tổng quan) → Participants & Reviews (xử lý đăng ký) → Check-in (vận hành thực tế tại hiện trường) — đúng chủ đề "theo dõi và vận hành sự kiện" nhóm/cá nhân em lựa chọn; (2) trong quá trình khảo sát thực tế, em phát hiện cả 4 thẻ KPI trên Dashboard bị kẹt ở trạng thái loading (skeleton placeholder), không hiển thị số liệu thật — đây là một bug tiềm năng thật sự, phù hợp với mục tiêu cốt lõi của kiểm thử là tìm ra lỗi ảnh hưởng đến chất lượng sản phẩm. |


---

## 2. Task 1B — Checklist Execution Results

> Chi tiết đầy đủ nằm ở file `04_checklist_execution.md`. Phần này tóm tắt.

| Screen | Số item Pass | Số item Fail | Tỷ lệ Pass |
|---|---|---|---|
| Screen 1 | | | |
| Screen 2 | | | |
| Screen 3 | | | |
| **Tổng** | | | |

**Tóm tắt các bug phát hiện:** (chi tiết ở `05_bug_reports.md`)
- [Bug 1 — mức độ nghiêm trọng]
- [Bug 2 — mức độ nghiêm trọng]
- ...

---

## 3. Task 2 — Usability Report

> Chi tiết đầy đủ nằm ở file `06_usability_testing.md`. Phần này tóm tắt kết quả chính.

**Task scenario đưa cho 5 người dùng:** [Tóm tắt 1-2 câu]

**Kết quả tổng quan:**
| Metric | Giá trị |
|---|---|
| Task success rate | [x/5 completed] |
| Thời gian trung bình | [phút] |
| Số lỗi/hesitation trung bình | |
| Điểm SUS trung bình | [0-100] |

**Top 3 findings nghiêm trọng nhất:**
1. [Finding — severity x/4]
2. [Finding — severity x/4]
3. [Finding — severity x/4]

---

## 4. Task 3 — Cross-Platform Report

> Chi tiết đầy đủ nằm ở file `07_cross_platform_matrix.md`. Phần này tóm tắt.

**Số cell đã test:** [x cells]
**Số cell Pass / Fail:** [x Pass / y Fail]

**Các lỗi rendering/layout đáng chú ý:**
| Screen | OS/Browser/Device | Lỗi |
|---|---|---|
| | | |

---

## 5. Kết luận & Đề xuất tổng thể

[Viết 1 đoạn tổng kết: scenario của bạn có vấn đề usability nào nổi bật nhất, đề xuất ưu tiên sửa gì trước]

---

## 6. Danh mục file đính kèm

- `01_GROUP_gui_checklist.md` (dùng chung nhóm)
- `04_checklist_execution.md`
- `05_bug_reports.md`
- `06_usability_testing.md`
- `07_cross_platform_matrix.md`
- `08_bug_usability_findings_log.md`
- `09_ai_audit_report.md`
- `10_ai_critique.md`
- `11_git_commit_log.md`
- `12_agent_skill_demo.md`
- `README.md`
- Thư mục ảnh/screenshots: `/screenshots/`