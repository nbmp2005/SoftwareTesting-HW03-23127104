# HW03 — Main Report
## GUI & Usability Testing on EMS (Event Management System)

**Họ tên:** Nguyễn Bình Minh Phương
**MSSV:** 23127104
**Hệ thống kiểm thử:** https://prod-dev.ems-fitus.cloud

---

## 1. Scenario & Screens

### 1.1. Scenario đã chọn
**Scenario A — Admin manages events.**

### 1.2. Danh sách screens đã chọn và lý do

| # | Screen | Mô tả ngắn | Lý do chọn |
|---|---|---|---|
| 1 | (A4) Participants & Reviews approval | Bao gồm 3 tab con trong cùng 1 trang chi tiết sự kiện: Registrants (danh sách người tham gia nói chung), Review Lecturers (duyệt riêng cho giảng viên), Review Students (duyệt riêng cho sinh viên). Cả 3 tab dùng chung layout bảng, bộ lọc Status, và nút Export. | Đây là screen được đề bài gợi ý trực tiếp (A4). Được chọn vì có độ phức tạp UI cao nhất trong Pool A: (1) 6 màu trạng thái đòi hỏi tính nhất quán và khả năng phân biệt rõ ràng (IA-04), dễ gây nhầm lẫn nếu không có chú thích; (2) có ràng buộc nghiệp vụ đặc thù — nếu một giảng viên đăng ký nhiều vai trò trong cùng một lượt đăng ký, admin bắt buộc phải duyệt/từ chối HẾT tất cả vai trò rồi mới được bấm Apply, đây là logic dễ phát sinh lỗi validate; (3) progress bar và Export là các thành phần feedback/state giàu tiềm năng phát hiện bug. Tổng hợp lại, đây là screen có xác suất cao nhất để tìm ra bug thật và vấn đề usability đáng phân tích. |
| 2 | (A5) Check-in tab | Màn hình admin dùng để quét mã QR/barcode của người tham dự khi đến sự kiện, xử lý 4 trạng thái quét khác nhau (SUCCESS, ALREADY_CHECKED_IN, OUTSIDE_CHECKIN_WINDOW, PENDING_REVIEW — cần Accept/Decline), có nhật ký quét (log) cập nhật real-time và chức năng xuất Excel lịch sử quét. | Được đề bài gợi ý trực tiếp (A5). Được chọn vì đây là screen có nhiều trạng thái hệ thống (system status) nhất trong toàn bộ Pool A — rất phù hợp để kiểm thử IA-04 (feedback/state) và đánh giá mức độ tin cậy (trust) của người dùng vào kết quả hệ thống hiển thị. Yêu cầu real-time update của log cũng là điểm dễ phát sinh lỗi đồng bộ dữ liệu, một dạng bug phổ biến nhưng khó phát hiện nếu chỉ dùng checklist UI tổng quát. |
| 3 | Screen tự chọn — Admin Dashboard (KPIs) | Trang đầu tiên admin nhìn thấy sau khi đăng nhập, hiển thị 4 chỉ số tổng quan: Total Events, Total Check-ins, Attendance Rate, Total Users. | Mặc dù không nằm trong 5 screen gợi ý cụ thể (A1–A5) của mục 5, Dashboard được liệt kê chính thức là một phần của Pool A trong mục 4 của đề bài ("Dashboard KPIs..."), nên vẫn thuộc đúng function group "quản trị sự kiện". Việc chọn thêm screen này được đề bài cho phép ở mục 5. Lý do cụ thể: (1) Dashboard tạo thành một luồng logic hoàn chỉnh cùng A4 và A5 — Dashboard (giám sát tổng quan) → Participants & Reviews (xử lý đăng ký) → Check-in (vận hành thực tế tại hiện trường); (2) trong khảo sát thực tế, phát hiện các thẻ KPI từng bị kẹt ở trạng thái loading, không hiển thị số liệu thật — một bug tiềm năng đáng theo dõi. |

Cả 3 screen đều thuộc route `/dashboard/admin/...` và được test trên cùng một event (ID 68 ở Task 1B/2, ID 141 ở Task 3 do khác batch dữ liệu demo), đảm bảo tính nhất quán trong đánh giá luồng "giám sát → xử lý đăng ký → vận hành tại cửa".

---

## 2. Task 1B — Checklist Execution Results (chi tiết)

> File nguồn: `04_checklist_execution.md`. Checklist gồm 4 nhóm tiêu chí (IA-01 General UI, IA-02 Forms, IA-03 Navigation, IA-04 Feedback & State), áp dụng cho mỗi screen (12–14 item/nhóm × 4 nhóm = 50 item/screen).

### 2.1. Kết quả tổng quan theo screen

| Screen | Pass | Fail | N/A | % Pass (đã test) | % Pass (tổng 50) |
|---|---|---|---|---|---|
| A4: Participants & Reviews | 24 | 6 | 20 | 80.0% (24/30) | 48.0% (24/50) |
| A5: Check-in tab | 21 | 4 | 25 | 84.0% (21/25) | 42.0% (21/50) |
| Screen 3: Admin Dashboard (KPIs) | 11 | 2 | 37 | 84.6% (11/13) | 22.0% (11/50) |
| **Tổng (150 item)** | **56** | **12** | **82** | **82.4% (56/68)** | **37.3% (56/150)** |

**Nhận xét về tỷ lệ N/A cao (82/150 = 54.7%):** phần lớn N/A tập trung ở nhóm **IA-02 Forms** (31/36 item của nhóm này trên cả 3 screen là N/A) — điều này hợp lý vì cả 3 screen đều là màn hình *xem/quản lý dữ liệu dạng bảng*, không phải form nhập liệu nhiều trường; N/A ở đây phản ánh đúng tính không áp dụng được của tiêu chí, không phải khoảng trống kiểm thử. Ngược lại, tỷ lệ Pass/Fail trên các item **có áp dụng được** (82.4%) mới là chỉ số phản ánh đúng chất lượng thực thi UI.

### 2.2. Kết quả chi tiết theo từng nhóm IA (breakdown)

**Screen A4 — Participants & Reviews:**

| Nhóm IA | Pass | Fail | N/A | Tổng |
|---|---|---|---|---|
| IA-01 General UI | 7 | 3 | 2 | 12 |
| IA-02 Forms | 1 | 0 | 11 | 12 |
| IA-03 Navigation | 7 | 1 | 4 | 12 |
| IA-04 Feedback | 9 | 2 | 3 | 14 |
| **Tổng** | **24** | **6** | **20** | **50** |

**Screen A5 — Check-in tab** *(Event tested: Machine Learning Hands-On Workshop, ID 68; check-in chưa mở tại thời điểm test → nhiều item IA-02/IA-04 bị N/A vì không thể mô phỏng luồng scan thật)*:

| Nhóm IA | Pass | Fail | N/A | Tổng |
|---|---|---|---|---|
| IA-01 General UI | 7 | 1 | 4 | 12 |
| IA-02 Forms | 4 | 0 | 8 | 12 |
| IA-03 Navigation | 7 | 1 | 4 | 12 |
| IA-04 Feedback | 3 | 2 | 9 | 14 |
| **Tổng** | **21** | **4** | **25** | **50** |

**Screen 3 — Admin Dashboard (KPIs):**

| Nhóm IA | Pass | Fail | N/A | Tổng |
|---|---|---|---|---|
| IA-01 General UI | 7 | 1 | 4 | 12 |
| IA-02 Forms | 0 | 0 | 12 | 12 |
| IA-03 Navigation | 4 | 1 | 7 | 12 |
| IA-04 Feedback | 0 | 0 | 14 | 14 |
| **Tổng** | **11** | **2** | **37** | **50** |

**Quan sát chéo giữa 3 screen:** nhóm **IA-01 General UI** có tỷ lệ Fail giống nhau ở cả 3 screen (mỗi screen Fail đúng tiêu chí IA-01-07 — Responsive), cho thấy đây là lỗi ở tầng layout dùng chung (shared layout/sidebar component) chứ không phải lỗi cục bộ từng trang. Nhóm **IA-02 Forms** gần như toàn N/A ở cả 3 screen do đặc thù các screen này thiên về hiển thị bảng dữ liệu.

### 2.3. Danh sách đầy đủ các item Fail (12 item)

**Screen A4 (6 Fail):**

| ID | Mô tả lỗi | Heuristic | Severity | Ref |
|---|---|---|---|---|
| IA-01-04 | Đa ngôn ngữ lỗi: role hiển thị sai thành "học viên tham dự" khi đã chuyển sang tiếng Anh | Nielsen #4: Consistency | 2 | F-001 |
| IA-01-06 | Không có loading state/skeleton khi dữ liệu tải chậm | Nielsen #1: Visibility | 1 | F-002 |
| IA-01-07 | Trang không responsive trên các kích thước màn hình | Nielsen #4: Consistency | 3 | F-003 |
| IA-03-03 | Nút Back không giữ trạng thái phân trang: đổi số dòng thành 50, vào chi tiết sự kiện rồi Back → tự reset về 5 dòng | Nielsen #3: User Control | 3 | F-004 |
| IA-04-10 | Không hiển thị thông báo khi mất kết nối mạng, trang bị đứng im lặng | Nielsen #1: Visibility | 2 | F-005 |
| IA-04-14 | Nút "Cancel All" không bị disable dù không có tác dụng gì khi bấm | Norman: Feedback + Signifiers | 2 | F-006 |

**Screen A5 (4 Fail):**

| ID | Mô tả lỗi | Heuristic | Severity | Ref |
|---|---|---|---|---|
| IA-01-07 | Ở viewport 375px: sidebar admin không collapse, đè lên nội dung chính | Nielsen #4: Consistency | 3 | F-007 |
| IA-03-11 | URL không cập nhật parameter khi chuyển giữa sub-tab "Checked In" / "Scan Logs" → không deep-link được | Nielsen #4: Consistency | 2 | F-008 |
| IA-04-01 | Click "Export" với bảng rỗng ("No results") không kích hoạt bất kỳ toast/feedback nào | Norman: Feedback | 2 | F-009 |
| IA-04-14 | Nút "Export" khi bảng rỗng vẫn enabled/clickable nhưng không có phản hồi (không toast, không file, không API call) | Norman: Feedback + Signifiers | 2 | F-010 |

**Screen 3 — Dashboard (2 Fail):**

| ID | Mô tả lỗi | Heuristic | Severity | Ref |
|---|---|---|---|---|
| IA-01-07 | Ở 375px: sidebar giữ nguyên 256px, nội dung chính tràn lề ngang (487px > 375px); nút hamburger tồn tại (`lg:hidden`) nhưng không thực sự collapse sidebar | Nielsen #4: Consistency | 3 | F-011 |
| IA-03-02 | Active state không hiển thị trên sidebar khi ở route root `/dashboard/admin` — cả 7 link đều `text-gray-400` (inactive), không có `aria-current="page"` | Nielsen #1: Visibility | 1 | F-012 |

### 2.4. Nhận xét tổng thể Task 1B

Vấn đề nổi bật nhất qua checklist là **IA-01-07 (Responsive) Fail trên cả 3/3 screen** — một lỗi hệ thống ở tầng layout, không phải lỗi cục bộ. Đứng thứ hai là nhóm lỗi thuộc **Nielsen #1 (Visibility of system status)**: thiếu loading state (F-002), thiếu cảnh báo mất mạng (F-005), thiếu active state ở trang gốc (F-012) — cho thấy hệ thống có xu hướng "im lặng" khi cần phản hồi trạng thái cho người dùng, một pattern sẽ được đối chiếu lại ở Mục 5 với kết quả Task 2 (Trust score thấp).

---

## 3. Task 2 — Usability Testing Report (chi tiết)

> File nguồn: `06_usability_testing.md`.

### 3.1. Thiết kế nghiên cứu

**Task scenario:** Người tham gia đóng vai nhân viên vận hành một sự kiện của trường sắp diễn ra, được giao nhiệm vụ (1) xử lý những người đang chờ duyệt đăng ký — chấp nhận người hợp lệ, và (2) xử lý check-in cho một người mới vừa đến sự kiện, xác nhận hệ thống đã ghi nhận thành công.

**Metrics đo:** Task success (Completed/Partial/Failed), Time on task, Error/hesitation count, SUS score (10 câu, thang 1–5).

**Probe questions** (hỏi sau SUS, ở cuối mỗi session): Q1 Clarity, Q2 Error recovery, Q3 Speed, Q4 Trust.

**Pilot session:** 1 người (Dương T. L, 28/07/2026) — không phát hiện vấn đề, không cần điều chỉnh kịch bản trước khi chạy 5 session chính thức.

**Người tham gia chính thức (5 người):**

| # | Vai trò | Ghi chú |
|---|---|---|
| P1 | Student FIT | |
| P2 | Student FIT | |
| P3 | Student FIT | |
| P4 | Student | |
| P5 | Student FIT | |

### 3.2. Tóm tắt từng session

| Participant | Task success | Time on task | Lỗi/hesitation | Điểm SUS/100 | Vấn đề chính quan sát được |
|---|---|---|---|---|---|
| **P1** | Partial | 05:30 | 9 | 42.5 | Không nhận biết tab dưới header do thiếu padding + màu tab giống nền; phải rà chuột mới tìm ra icon "mắt" để xem chi tiết (kỳ vọng click cả dòng); phải cuộn ngang bảng sự kiện mà không biết trước có thể cuộn; cột quan trọng (số HV/GV, thời gian đăng ký) nằm cuối bảng, không liền kề; mất kết quả search khi Back từ trang chi tiết; nút "All status"/"All time" hiện dropdown thay vì điều hướng như kỳ vọng; nhầm ô "Go to page" là nút bấm; đổi 100 dòng/trang thì thanh phân trang bị đẩy quá xa. Ngoài ra P1 còn nghi vấn thiếu validate ngày đăng ký > ngày check-in (được ghi nhận là Bug riêng, không tính vào usability finding). |
| **P2** | Completed | 03:00 *(xem lưu ý bên dưới)* | 1 | 65.0 | Bối rối không biết nhấn xác nhận duyệt ở đâu, mất vài giây suy nghĩ; không biết lấy mã (member code/barcode) ở đâu để check-in nên lần đầu nhập ký tự ngẫu nhiên, phải có chỉ dẫn mới tìm được mã. |
| **P3** | Completed | 04:00 | 1 | 75.0 | Nhìn qua các tab nhiều lần, không rõ tab nào dẫn tới màn hình duyệt đăng ký; không có tiêu chí/trạng thái nào giúp phân biệt học viên/giảng viên "hợp lệ" trước khi duyệt; không xác định được cách lấy mã code để check-in. |
| **P4** | Completed | 01:00 | 0 | 50.0 | Bấm vào tên sự kiện không mở chi tiết (gây bối rối ban đầu); danh sách Review chỉ hiện dạng hàng, không dẫn tới thông tin chi tiết người dùng nên không biết cách xác minh tính hợp lệ trước khi duyệt. |
| **P5** | Completed | 08:41 | 2 | 35.0 | Loay hoay không tìm được đường vào trang admin; bấm vào tên sự kiện chờ trang chi tiết hiện ra nhưng không có phản hồi; lọc theo Pending rồi không thấy nút duyệt, phải mở User Guide mới biết; không tìm thấy mã code của học sinh để check-in, định thoát ra tạo tài khoản sinh viên mới chỉ để lấy mã. |

*Lưu ý: dữ liệu gốc của P2 có một điểm chưa nhất quán giữa ghi chú "Time on task: 01:15" trong log quan sát và giá trị "03:00" dùng trong bảng tổng hợp Metrics gốc — báo cáo này dùng giá trị đã được dùng để tính trung bình toàn nhóm (03:00) để đảm bảo nhất quán với con số trung bình 04:26 bên dưới; nên đối chiếu lại video recording (https://youtu.be/p3lxP7p3pfs) nếu cần độ chính xác tuyệt đối cho riêng session này.*

### 3.3. Kết quả tổng hợp Metrics

| Metric | Giá trị |
|---|---|
| Task success rate | 4/5 completed, 1/5 partial (80.0% completed) |
| Thời gian trung bình | 04:26 (phút:giây) |
| Số lỗi/hesitation trung bình | 2.6 |
| Điểm SUS trung bình | **53.5/100** (min 35.0 — P5, max 75.0 — P3) |

### 3.4. Điểm SUS chi tiết theo câu hỏi

| Câu | P1 | P2 | P3 | P4 | P5 |
|:---:|:---:|:---:|:---:|:---:|:---:|
| Q1 | 1 | 3 | 3 | 2 | 1 |
| Q2 | 3 | 3 | 2 | 3 | 5 |
| Q3 | 1 | 4 | 4 | 3 | 3 |
| Q4 | 1 | 1 | 1 | 1 | 2 |
| Q5 | 3 | 3 | 3 | 2 | 2 |
| Q6 | 5 | 4 | 3 | 5 | 4 |
| Q7 | 2 | 2 | 5 | 2 | 2 |
| Q8 | 5 | 2 | 2 | 3 | 4 |
| Q9 | 5 | 5 | 4 | 4 | 3 |
| Q10 | 1 | 1 | 1 | 1 | 2 |
| **SUS/100** | **42.5** | **65.0** | **75.0** | **50.0** | **35.0** |

**Diễn giải:** điểm SUS trung bình 53.5/100 thấp hơn benchmark ngành phổ biến (~68/100) khoảng 14.5 điểm, và chỉ 1/5 participant (P3) đạt điểm trên benchmark này. Độ phân tán rất lớn (35–75, biên độ 40 điểm) cho thấy trải nghiệm không tệ đồng đều trên toàn hệ thống mà phụ thuộc mạnh vào việc participant đó có "mò" được các điểm chặn cụ thể (vị trí duyệt Pending, cách lấy mã check-in) hay không — ai gặp phải cả 2 điểm chặn này (P5) có điểm thấp nhất; ai né được hoặc tìm ra nhanh (P3, dù vẫn phải hỏi) có điểm cao hơn hẳn.

Đáng chú ý: **câu hỏi SUS số 9 ("Tôi cảm thấy tự tin khi sử dụng hệ thống")** có điểm cao ở mọi participant (Q9 trong bảng = item 9 gốc) trong khi câu hỏi probe riêng về Trust ("bạn có tin chắc hệ thống đã ghi nhận đúng hành động của mình không?") lại nhận phản hồi tiêu cực từ nhiều người (P2 "Không hoàn toàn tin tưởng", P3 "Không tin"). Điều này cho thấy có sự khác biệt giữa "tự tin thao tác" và "tin tưởng kết quả hệ thống ghi nhận" — một khoảng trống về **feedback xác nhận hành động**, khớp với các Fail liên quan Nielsen #1 (Visibility) ở Task 1B (xem Mục 5.2).

### 3.5. Ranked Findings (đầy đủ 11 finding, Severity 0–4)

| # | Finding | Type | Phạm vi | Sev. | Người gặp | Đề xuất khắc phục |
|---|---|---|---|---|---|---|
| 1 | Không tìm thấy mã code/QR để check-in — nhầm lẫn "barcode" (label) vs "Member code" (dữ liệu thực) | Usability | Systemic | **4** | P3, P5 | Hiển thị rõ khu vực "Nhập Member code" ngay trên màn hình Check-in, label nhất quán, không cần suy luận |
| 2 | Không tìm được nơi duyệt đăng ký Pending — phải mở User Guide mới biết | Usability | Systemic | **4** | P3, P5 | Thêm badge số lượng "Pending" trên tab liên quan; đổi tên tab rõ nghĩa hơn (vd "Duyệt đăng ký") |
| 3 | Bấm vào tên sự kiện không mở chi tiết — phải dùng đúng icon con mắt, khác hành vi quen thuộc | Usability | Systemic | 3 | P1, P4, P5 | Cho phép row-click mở chi tiết, giữ icon mắt như lối tắt phụ |
| 4 | Kết quả search bị mất khi quay lại danh sách sau khi xem chi tiết sự kiện | Bug | Isolated | 3 | P1 | Giữ query/filter state khi back (URL params hoặc session state) |
| 5 | Thiếu validate: ngày đăng ký có thể diễn ra sau ngày check-in | Bug | Isolated | 3 | P1 | Thêm validate registration date ≤ check-in date ở form Add/Edit Event |
| 6 | Web chậm liên tục, không có loading state | Usability | Isolated | 3 | P3 | Thêm spinner, áp dụng Lazy Loading + Caching |
| 7 | Review chỉ hiện dạng hàng, không link tới thông tin chi tiết participant | Usability | Isolated | 2 | P4 | Thêm link/click-through sang thông tin participant liên quan |
| 8 | Bảng sự kiện quá nhiều cột, phải cuộn ngang mà không biết trước; cột quan trọng nằm cuối, không liền kề | Usability | Isolated | 2 | P1 | Ưu tiên cột quan trọng ở đầu bảng; thêm chỉ báo trực quan có thể cuộn ngang |
| 9 | Nút "All status"/"All time" hiện dropdown thay vì điều hướng, không khớp kỳ vọng | Usability | Isolated | 2 | P1 | Thêm icon chevron trên nút dropdown để phân biệt nút điều hướng |
| 10 | Header/tab thiếu padding, màu tab gần giống màu nền, khó nhận biết | Usability | Isolated | 2 | P1 | Tăng contrast tab active/inactive; thêm padding dưới header |
| 11 | Thanh chuyển trang bị đẩy quá xa khi chọn 100 dòng/trang | Usability | Isolated | 1 | P1 | Sticky pagination ở cuối viewport thay vì cuối bảng |

### 3.6. Prioritised Recommendations

1. **[Ưu tiên cao nhất]** Làm rõ luồng check-in (đổi label sang "Member code" thay vì "barcode") và luồng duyệt đăng ký (vị trí tab, badge Pending) — 2 finding Systemic severity 4, trực tiếp chặn nhiệm vụ chính, mỗi finding ảnh hưởng 2/5 participant (Finding #1, #2).
2. **[Ưu tiên cao]** Đổi hành vi click sự kiện: cho phép click cả dòng thay vì chỉ icon mắt — finding Systemic, ảnh hưởng 3/5 participant (Finding #3).
3. **[Ưu tiên trung bình]** Sửa logic validate ngày đăng ký/check-in và giữ lại state search khi back — cả hai là lỗi chức năng (Bug) (Finding #4, #5).
4. **[Ưu tiên trung bình]** Bổ sung tiêu chí hợp lệ trong danh sách chờ duyệt và link review → chi tiết participant, giúp admin ra quyết định nhanh, chính xác hơn (Finding #6, #7).
5. **[Ưu tiên thấp]** Các cải tiến UI nhỏ: contrast tab/header, chỉ báo cuộn ngang, phân biệt input "Go to page" với nút bấm, sticky pagination (Finding #8–11).

### 3.7. Kết luận Usability

Điểm SUS trung bình 53.5/100 xếp vào mức "below average" theo thang Bangor, thấp hơn benchmark ngành (68/100) khoảng 14.5 điểm. Độ phân tán lớn (35–75) cho thấy vấn đề không nằm ở toàn hệ thống một cách đồng đều mà tập trung vào các điểm chặn cụ thể trong luồng task: 3 finding Systemic — không biết mã check-in là gì, không tìm thấy nơi duyệt đăng ký, và hành vi click sự kiện không nhất quán — đều liên quan trực tiếp đến khả năng hoàn thành nhiệm vụ chính (duyệt đăng ký + check-in), không phải vấn đề thẩm mỹ phụ. Đề xuất tổng thể: ưu tiên khắc phục 3 finding Systemic (Finding #1–3) trước vì ảnh hưởng nhiều người và chặn trực tiếp task chính, sau đó mới xử lý các cải tiến UI nhỏ lẻ còn lại.

---

## 4. Task 3 — Cross-Platform Compatibility Report (chi tiết)

> File nguồn: `07_cross_platform_matrix.md`.

### 4.1. Phạm vi kiểm thử

15 cell = 5 cấu hình (Windows/Chrome/Desktop, Windows/Firefox/Desktop, macOS/Edge/Desktop, Android/Samsung Internet/Tablet, iOS/Safari/Phone) × 3 screens (Dashboard, A4, A5). Coverage: **4 OS, 5 Browser, 3 Device class**.

### 4.2. Kết quả theo screen

| Screen | Pass | Fail | Cấu hình Fail |
|---|---|---|---|
| Dashboard (KPIs) | 4/5 | 1/5 | iOS Safari Phone |
| A4 — Participants & Reviews | 3/5 | 2/5 | Android Samsung Internet Tablet, iOS Safari Phone |
| A5 — Check-in tab | 3/5 | 2/5 | Android Samsung Internet Tablet, iOS Safari Phone |
| **Tổng (15 cell)** | **10** | **5** | |

### 4.3. Phân tích theo cấu hình (device/browser)

| Cấu hình | Kết quả trên 3 screen | Ghi chú |
|---|---|---|
| Windows / Chrome / Desktop | 3/3 Pass | Hoàn toàn ổn định |
| Windows / Firefox / Desktop | 3/3 Pass | Hoàn toàn ổn định |
| macOS / Edge / Desktop | 3/3 Pass | Hoàn toàn ổn định |
| Android / Samsung Internet / Tablet (768px) | 1/3 Pass, 2/3 Fail | Pass ở Dashboard; Fail ở A4 (horizontal overflow bảng) và A5 (grid 6 KPI card không wrap) |
| **iOS / Safari / Phone (390px)** | **0/3 Pass, 3/3 Fail** | **Fail ở cả 3 screen — cấu hình duy nhất fail 100%** |

→ Toàn bộ 3 cấu hình Desktop (Windows Chrome/Firefox, macOS Edge) Pass tuyệt đối 9/9 cell. Toàn bộ lỗi rendering (5/5) đều rơi vào 2 cấu hình mobile/tablet, và **riêng iOS Safari Phone fail ở cả 3 screen được test** — đây là cấu hình rủi ro cao nhất trong toàn bộ ma trận.

### 4.4. Chi tiết các lỗi rendering/layout

| Screen | OS/Browser/Device | Loại lỗi | Mô tả chi tiết |
|---|---|---|---|
| Dashboard | iOS / Safari / Phone (390px) | Non-responsive / Layout Broken | Tiêu đề Dashboard & các thẻ KPI bị tràn khỏi khung nhìn màn hình. |
| A4 — Review Students | Android / Samsung Internet / Tablet (768px) | Horizontal Overflow | Bảng dữ liệu 5 cột không có `overflow-x: auto` trên table wrapper, làm tràn lề toàn màn hình Tablet. |
| A4 — Review Students | iOS / Safari / Phone (390px) | Action Buttons Hidden / Broken Layout | Giao diện bị đẩy lệch khỏi lề phải; nút duyệt và ô tìm kiếm bị giấu sau viền màn hình. |
| A5 — Check-in | Android / Samsung Internet / Tablet (768px) | Grid Overflow | Grid 6 thẻ KPI (Total Check-ins, Lecturer, Student, Total Scans, Successful, Failed) không wrap ở 768px, làm vỡ khung Check-in. |
| A5 — Check-in | iOS / Safari / Phone (390px) | Unusable UI / Element Overlap | Sidebar làm lệch toàn bộ ô quét Barcode & bảng Scan Logs off-screen — không thể sử dụng tính năng Check-in trên Mobile Safari. |

### 4.5. Nhận xét Task 3

Kết quả cho thấy rõ ràng đây **không phải lỗi tương thích trình duyệt (browser-specific bug)** theo nghĩa cổ điển (vd CSS prefix thiếu, API không hỗ trợ), mà là **thiếu breakpoint responsive** ở tầng layout dùng chung (sidebar + main content + component grid) — cùng một nguyên nhân gốc xuất hiện lặp lại ở mọi screen khi viewport thu nhỏ xuống dưới ngưỡng tablet/phone, bất kể nội dung cụ thể của từng trang.

---

## 5. Tổng hợp chéo giữa 3 phương pháp (Triangulation)

Đây là phần giá trị nhất của việc dùng 3 phương pháp song song: cùng một root cause thường được phát hiện độc lập bởi nhiều phương pháp khác nhau, giúp tăng độ tin cậy của finding.

### 5.1. Lỗi Responsive — được xác nhận độc lập bởi CẢ 2 phương pháp

| Phương pháp | Bằng chứng |
|---|---|
| Task 1B (heuristic expert review) | IA-01-07 Fail trên **cả 3/3 screen** (F-003, F-007, F-011) |
| Task 3 (cross-browser thực tế trên BrowserStack) | iOS Safari Phone Fail **cả 3/3 screen**; Android Tablet Fail **2/3 screen** (F-013, F-015, F-016, F-017 — trùng root cause với F-003/007/011) |

→ Đây là finding có độ tin cậy cao nhất trong toàn bộ báo cáo vì được xác nhận bằng 2 phương pháp độc lập (đánh giá heuristic tĩnh và test rendering thực tế trên thiết bị thật), không phải chỉ dựa trên nhận định chủ quan của một người kiểm thử. **Đây cũng là gap lớn nhất chưa được kiểm chứng bởi Task 2**, vì usability testing chỉ chạy trên desktop — nghĩa là mức độ ảnh hưởng thực tế của lỗi responsive lên trải nghiệm người dùng thật vẫn còn là một khoảng trống (xem Mục 6 — Hạn chế).

### 5.2. Thiếu "Visibility of system status" (Nielsen #1) — nối kết giữa checklist và điểm Trust thấp

Task 1B ghi nhận nhiều Fail thuộc heuristic Nielsen #1: thiếu loading state (F-002), không cảnh báo mất mạng (F-005), thiếu active-state chỉ báo vị trí hiện tại (F-012), không có toast khi Export rỗng (F-009). Độc lập với đó, Task 2 ghi nhận: mặc dù điểm SUS-item "tự tin thao tác" cao, **probe question về Trust lại nhận phản hồi tiêu cực từ 2/5 participant** ("Không tin", "Không hoàn toàn tin tưởng" khi được hỏi hệ thống có ghi nhận đúng hành động duyệt/check-in hay không). Hai kết quả này cùng trỏ về một root cause: hệ thống thực hiện hành động nhưng **không luôn xác nhận rõ ràng bằng tín hiệu trực quan**, khiến người dùng phải tự suy đoán liệu thao tác đã thành công hay chưa.

### 5.3. Navigation/Discoverability — checklist phát hiện triệu chứng, usability testing phát hiện mức độ nghiêm trọng thật

Task 1B ghi nhận 2 lỗi navigation ở mức "kỹ thuật": mất pagination state khi Back (F-004, Sev.3) và URL không đổi khi chuyển sub-tab (F-008, Sev.2) — cả hai đọc qua có vẻ là vấn đề nhỏ về state management. Nhưng khi quan sát người dùng thật ở Task 2, vấn đề navigation hoá ra nghiêm trọng hơn nhiều: **2 finding Systemic severity cao nhất trong toàn báo cáo (Sev.4)** đều là vấn đề "không tìm thấy" — không tìm thấy nơi duyệt Pending, không tìm thấy mã check-in — cho thấy vấn đề navigation của hệ thống không chỉ nằm ở việc giữ state (như checklist phát hiện) mà còn ở tầng sâu hơn: **thông tin/hành động quan trọng không được đặt ở nơi người dùng kỳ vọng tìm thấy**, một loại lỗi mà chỉ có thể phát hiện qua quan sát hành vi người dùng thật, không thể phát hiện chỉ bằng expert checklist.

**Kết luận Mục 5:** việc kết hợp 3 phương pháp cho thấy rõ giá trị bổ trợ của chúng — checklist tốt trong việc phát hiện lỗi kỹ thuật/tuân thủ heuristic có thể liệt kê tường minh, cross-browser test tốt trong việc xác nhận lỗi rendering thực tế trên thiết bị thật, còn usability testing là phương pháp DUY NHẤT phát hiện được mức độ nghiêm trọng thật sự đối với nhiệm vụ của người dùng — kể cả khi mọi tiêu chí checklist ở khu vực đó đều Pass.

---

## 6. Bug & Usability Findings Log — Tổng kết

> Chi tiết đầy đủ 28 finding: `08_bug_usability_findings_log.md`.

| Phân loại theo Type | Số lượng |
|---|---|
| Bug | 17 |
| Usability | 11 |
| **Tổng** | **28** |

| Phân loại theo Severity | Số lượng | ID |
|---|---|---|
| 0 – Cosmetic | 0 | — |
| 1 – Minor | 3 | F-002, F-012, F-028 |
| 2 – Moderate | 12 | F-001, F-005, F-006, F-008, F-009, F-010, F-014, F-016, F-024, F-025, F-026, F-027 |
| 3 – Major | 11 | F-003, F-004, F-007, F-011, F-013, F-015, F-017, F-020, F-021, F-022, F-023 |
| 4 – Critical | 2 | F-018, F-019 |

**Nhận xét:** 2/2 finding Critical đều thuộc Task 2 (usability testing) — một lần nữa củng cố nhận định ở Mục 5.3 rằng usability testing với người dùng thật là phương pháp phát hiện được các vấn đề nghiêm trọng nhất mà checklist tĩnh và cross-browser test không thể tự phát hiện.

---

## 7. Đề xuất ưu tiên tổng thể (Roadmap hợp nhất từ cả 3 task)

**P0 — Khắc phục ngay (chặn task chính, Sev.4):**
- F-018: Đổi label "barcode" → "Member code" nhất quán, hiển thị rõ khu vực nhập ngay trên màn hình Check-in.
- F-019: Thêm badge số lượng "Pending" trên tab liên quan; đổi tên tab rõ nghĩa (vd "Duyệt đăng ký").

**P1 — Ưu tiên cao (lỗi hệ thống lặp lại nhiều screen, xác nhận bởi 2 phương pháp độc lập):**
- F-003 / F-007 / F-011 / F-013 / F-015 / F-016 / F-017: Sửa breakpoint responsive dùng chung cho sidebar + main content + grid layout, áp dụng đồng bộ cho cả 3 screen thay vì sửa riêng lẻ.
- F-020: Cho phép row-click mở chi tiết sự kiện, giữ icon mắt như lối tắt phụ.

**P2 — Ưu tiên trung bình (Bug chức năng + gap về feedback):**
- F-004: Lưu pagination state vào URL params/session khi Back.
- F-021: Giữ query/filter state khi back về danh sách sau khi xem chi tiết.
- F-022: Validate registration date ≤ check-in date ở form Add/Edit Event.
- F-001: Sửa chuỗi dịch role name (i18n).
- F-005 / F-009 / F-010: Bổ sung feedback rõ ràng (toast/banner) cho mất mạng và Export rỗng; disable nút khi không có tác dụng.
- F-006: Disable "Cancel All" khi không có item để cancel.

**P3 — Ưu tiên thấp (cải tiến UI nhỏ, không chặn task):**
- F-002 / F-023: Thêm loading state/skeleton; áp dụng lazy loading & caching.
- F-012: Thêm nav item khớp route root, highlight đúng active state.
- F-008: Thêm query param cho sub-tab hiện tại để deep-link được.
- F-024: Link review → thông tin chi tiết participant.
- F-025 / F-026 / F-027 / F-028: Ưu tiên cột quan trọng đầu bảng, chỉ báo cuộn ngang, chevron cho dropdown, tăng contrast tab/header, sticky pagination.

---

## 8. Hạn chế của quá trình kiểm thử

- **Task 2 (usability testing) chỉ được thực hiện trên desktop**, trong khi Task 1B và Task 3 đều xác nhận lỗi responsive nghiêm trọng trên mobile/tablet (đặc biệt iOS Safari Phone fail 3/3 screen). Do đó, mức độ ảnh hưởng thực tế của lỗi responsive lên hành vi và cảm nhận của người dùng thật **vẫn chưa được đo lường trực tiếp** — đề xuất một vòng usability testing bổ sung trên thiết bị di động thật.
- **Cỡ mẫu Task 2 nhỏ (n=5)**, mang tính chất định tính (qualitative), phù hợp để phát hiện pattern chứ không đủ sức mạnh thống kê để suy rộng tỷ lệ chính xác cho toàn bộ người dùng.
- **Task 3 chỉ test 1 thiết bị đại diện cho mỗi device class** (1 Tablet Android, 1 Phone iOS) — chưa bao phủ các biến thể khác như iPad, Android phone, hay Firefox/Safari trên mobile.
- Một số item checklist (loading state dưới mạng chậm, real-time sync 2 thiết bị, mô phỏng mất mạng) được đánh dấu N/A do giới hạn môi trường test và **cần kiểm tra thủ công bổ sung**.
- Dữ liệu Session P2 (Task 2) có một điểm chưa nhất quán về Time on task giữa ghi chú quan sát và bảng tổng hợp (xem chú thích Mục 3.2) — nên đối chiếu lại video recording nếu cần độ chính xác tuyệt đối.

---

## 9. Kết luận & Đề xuất tổng thể

Cả 3 phương pháp kiểm thử đều hội tụ về hai nhóm vấn đề chính trong Scenario A (Admin manages events):

**Thứ nhất**, hệ thống **không responsive trên thiết bị di động/tablet** — đây là finding có độ tin cậy cao nhất vì được xác nhận độc lập bởi cả heuristic checklist (Fail 3/3 screen) lẫn kiểm thử thiết bị thật (iOS Safari Phone Fail 3/3 screen, Android Tablet Fail 2/3 screen), trong khi toàn bộ 3 cấu hình Desktop Pass tuyệt đối. Đây là lỗi ở tầng layout dùng chung, sửa một lần sẽ khắc phục đồng thời trên cả 3 screen.

**Thứ hai**, và nghiêm trọng hơn về mặt tác động đến người dùng, là **hai điểm chặn luồng nghiệp vụ chính** chỉ lộ ra qua usability testing: người dùng không biết lấy Member code ở đâu để check-in, và không tìm được nơi duyệt đăng ký Pending — cả hai đều severity 4/4, khiến chỉ 4/5 người hoàn thành được nhiệm vụ và điểm SUS trung bình chỉ đạt 53.5/100 (thấp hơn benchmark ngành ~14.5 điểm). Đáng chú ý, các vấn đề này gần như không thể phát hiện được chỉ bằng checklist heuristic tĩnh — minh chứng cho giá trị không thể thay thế của việc quan sát người dùng thật.

**Đề xuất ưu tiên tổng thể** (chi tiết ở Mục 7): (1) khắc phục 2 điểm chặn severity 4 trước tiên vì ảnh hưởng trực tiếp đến khả năng hoàn thành task chính; (2) sửa lỗi responsive dùng chung cho cả 3 screen vì đây là lỗi hệ thống được xác nhận bởi 2 phương pháp độc lập; (3) đổi hành vi click sự kiện sang row-click; (4) xử lý các Bug/Usability còn lại theo severity giảm dần. Song song đó, nên bổ sung một vòng usability testing trên thiết bị di động thật để lấp khoảng trống đã nêu ở Mục 8, vì hiện tại mức độ ảnh hưởng thực sự của lỗi responsive lên trải nghiệm người dùng vẫn chưa được đo lường trực tiếp.

---

## 10. Danh mục file đính kèm

- `01_GROUP_gui_checklist.md` (dùng chung nhóm)
- `03_main_report.md` (file này)
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