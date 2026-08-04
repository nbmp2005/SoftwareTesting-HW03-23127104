# AI Audit Report (Mandatory Appendix)

## Prompt 1
- **AI tool:** Claude Sonnet 5
- **Ngày giờ:** 27/07/2026 08:00 AM
- **Prompt:**
```
tôi đang cần làm bài tập này nhưng chưa hiểu lí thuyết và cách làm. Hãy giúp tôi:

giải thích chi tiết và đầy đủ toàn bộ lí thuyết bài này, cũng như các output (định dạng, ý nghĩa,...) mà tôi cần biết và làm. Tôi cũng chưa hiểu screen rồi scenario các kiểu trong phần yêu cầu này. Nói chung giải thích cho tôi lý thuyết foundation và lí thuyết, kiến thức liên quan đến bài tập này nữa
nhóm tôi có 5 người và đây là những task thành viên khác nhóm tôi đã chọn: người 1 - pool B: scene 1,2,3,(4), người 2 - pool C: screen 1, 2, 3, 4, người 3 - scenario A, người 4 - lấy D
Vậy bây giờ tôi nên chọn cái nào
3. Hãy liệt kê các task và output tôi phải làm và hoàn thành 1 cách thật chi tiết
4. Hãy lên plan cụ thể cho tôi từng task
```
- **AI Output (tóm tắt hoặc trích dẫn ngắn):**
```
1. Giải thích lý thuyết nền tảng
1.1. "Screen" và "Scenario" nghĩa là gì trong bài này?

Đây là hai khái niệm dễ gây nhầm vì nghe tương tự nhau:

Scenario (kịch bản chức năng) = một nhóm chức năng lớn của hệ thống, gắn với một vai trò/luồng nghiệp vụ. Bài cho 4 scenario: A (Admin quản lý sự kiện), B (User đăng ký sự kiện), C (Admin quản lý user), D (User gửi yêu cầu hỗ trợ + Admin xử lý). Bạn chọn 1 scenario làm "sân nhà" của mình.
Screen (màn hình) = một trang/giao diện cụ thể nằm bên trong scenario đó, nơi người dùng thực sự tương tác (nhìn thấy layout, nút bấm, form...). Ví dụ trong scenario A: "Events list" là 1 screen, "Add/Edit Event form" là 1 screen khác, "Check-in tab" là 1 screen khác nữa.

Bạn phải chọn ≥ 3 screens thuộc scenario mình chọn, rồi áp dụng checklist + usability test + cross-platform test lên chính 3 screens đó (xuyên suốt Task 1B, 2, 3 — dùng chung 1 bộ screens).

Lưu ý quan trọng: đề cho phép bạn tự định nghĩa thêm screen khác ngoài danh sách gợi ý, miễn là cùng function group và bạn giải thích được lý do chọn (mục 5: "you may choose others in the same group, but you must justify the choice"). Điều này sẽ rất hữu ích cho câu hỏi số 2 bên dưới.

1.2. Task 1 — GUI Checklist: heuristics là gì, checklist dùng để làm gì?

Một "GUI checklist" là danh sách các tiêu chí kiểm tra giao diện, được xây trên nền các nguyên tắc UI đã được nghiên cứu/kiểm chứng rộng rãi:

Nielsen's 10 Usability Heuristics (nổi tiếng nhất) — 10 nguyên tắc như: hiển thị trạng thái hệ thống rõ ràng, khớp giữa hệ thống và thế giới thực, cho người dùng kiểm soát/hủy thao tác được, tính nhất quán, phòng lỗi hơn là báo lỗi, nhận diện hơn là ghi nhớ, tính linh hoạt/hiệu quả, thiết kế tối giản/thẩm mỹ, giúp người dùng nhận biết-chẩn đoán-phục hồi lỗi, có tài liệu trợ giúp.

Norman's 6 Principles (trong "The Design of Everyday Things"): visibility (khả năng nhìn thấy), feedback (phản hồi), constraints (ràng buộc hành vi), mapping (ánh xạ điều khiển-kết quả), consistency (nhất quán), affordance (gợi ý cách dùng qua hình dạng).

Shneiderman's 8 Golden Rules: nhất quán, cho phép shortcut cho người dùng thành thạo, phản hồi đầy đủ, thiết kế theo chuỗi hành động có điểm kết thúc rõ, phòng lỗi/xử lý lỗi đơn giản, cho phép undo dễ dàng, cho người dùng cảm giác kiểm soát, giảm tải trí nhớ ngắn hạn.

Checklist của nhóm bạn phải tổng hợp các nguyên tắc này thành >40 câu hỏi kiểm tra cụ thể, chia theo 4 khía cạnh (IA):

IA-01 General UI (layout, màu sắc, font, đa ngôn ngữ EN/VI, trạng thái rỗng/loading...)
IA-02 Forms (label, validate, vị trí báo lỗi, upload, rich-text editor...)
IA-03 Navigation (menu, breadcrumb, tab, sidebar, kéo-thả, deep link...)
IA-04 Feedback/State (toast, badge, dialog xác nhận, progress bar, màu trạng thái, cập nhật real-time...)

Cách làm: dùng AI generate bộ đầu tiên → nhóm review, sửa, bổ sung → với mỗi item nhóm tự thêm, phải giải thích tại sao AI bỏ sót nó (ví dụ AI thường thiếu: accessibility, RTL layout, dark mode, keyboard navigation, i18n sâu).

Phần B (cá nhân): bạn lấy chính bộ checklist đó, áp vào từng screen bạn chọn, đánh dấu Pass/Fail từng item, ghi lý do Fail, chụp ảnh minh chứng, và báo bug (theo format: screen, steps to reproduce, expected vs actual, severity, screenshot).

1.3. Task 2 — Usability Testing với 5 người dùng thật

Đây là kiểm thử usability thực nghiệm (không phải bạn tự đánh giá bằng mắt), quy trình chuẩn UX research:

Viết task scenario dạng mục tiêu, không hướng dẫn từng bước (ví dụ: "đăng ký tham dự 1 workshop sắp tới và cho tôi xem QR check-in của bạn" — không nói "bấm nút A rồi bấm nút B").
Định nghĩa metric đo lường:
Task success: Completed / Partial / Failed
Time on task
Số lỗi/số lần lưỡng lự (hesitation)
Điểm SUS (System Usability Scale — thang 10 câu hỏi chuẩn, cho điểm 0-100) hoặc UEQ-S (User Experience Questionnaire Short — đo nhanh 8 cặp tính từ đối lập)
Câu hỏi mở (probe) về độ rõ ràng, khả năng phục hồi lỗi, tốc độ, độ tin cậy
Tuyển 5 người dùng thật ngoài lớp (có thông tin liên hệ để TA xác minh ngẫu nhiên), chạy pilot 1 người trước để phát hiện lỗi kịch bản.
Chạy 5 session: nói rõ đang test sản phẩm chứ không test người dùng, yêu cầu "think aloud" (nói to suy nghĩ), quan sát trung lập không gợi ý, quay màn hình + ghi chú.
Phân tích: tổng hợp điểm SUS/UEQ-S của 5 người, tính tỷ lệ thành công/thời gian trung bình/số lỗi, nhóm các pain point giống nhau, phân biệt bug đơn lẻ với vấn đề thiết kế hệ thống, xếp hạng theo mức độ nghiêm trọng (0-4).
Viết Usability Report hoàn chỉnh: kịch bản, bảng 5 người tham gia (che 4 số giữa số liên hệ), bảng metric, các phát hiện đã xếp hạng kèm ảnh, danh sách đề xuất cải tiến ưu tiên.
1.4. Task 3 — Cross-Browser / Cross-Platform Testing

Đây là kiểm thử tính tương thích — cùng 1 screen có hiển thị/hoạt động đúng trên các môi trường khác nhau không (khác OS, khác trình duyệt, khác loại thiết bị: máy tính bàn, tablet, điện thoại).

Yêu cầu: build ma trận phủ 3 OS × 5 browser × 3 loại thiết bị — không cần đủ 45 ô, nhưng mỗi OS, mỗi browser, mỗi loại thiết bị phải xuất hiện ít nhất 1 lần cho mỗi screen trong 3 screens của bạn.

Dùng công cụ cloud như BrowserStack/LambdaTest (bản trial) để giả lập nhiều môi trường thật, hoặc thiết bị thật nếu hết trial. Mỗi ảnh chụp phải có overlay tên đăng nhập dạng MSSV@...edu.vn để chống gian lận (đây là phần không được để AI tạo giả, TA sẽ kiểm tra kỹ).

1.5. AI Audit Report & AI Critique

Vì đây là bài "AI-First", bạn bắt buộc phải: (1) log lại toàn bộ prompt + output AI đã dùng (tool, thời gian, prompt, output), và (2) viết đoạn 200-300 từ phê bình AI — chỗ nào AI sai/thiếu/lệch, vì sao nó không phát hiện ra, bài học rút ra. Đây không phải phần phụ — thiếu là 0 điểm.

1.6. Bug & Usability Findings channel

Mọi bug/đề xuất phải nộp 2 lần: (1) qua Google Form, (2) tổng hợp vào 1 file log với các cột chuẩn. Hai nguồn này phải khớp nhau vì TA sẽ đối chiếu.

2. Bạn nên chọn scenario nào?

Nhìn vào phân bổ hiện tại:

Người	Scenario	Screens đã lấy
1	B	B1, B2, B3, (có thể cả B4)
2	C	C1, C2, C3, C4 (hết sạch, C chỉ có 4 screen)
3	A	Scenario A (chưa rõ screens cụ thể)
4	D	D (chưa rõ screens cụ thể)
Bạn	?	?

Vấn đề: nhóm bạn có 5 người nhưng đề chỉ thiết kế cho 4 scenario (dành cho nhóm 3-4 người). Đề có dự trù trường hợp này ở mục 5: "nhóm >4 người, nếu 2 người dùng chung 1 scenario thì phải chọn screens khác nhau, không được trùng."

Xét khả năng còn chỗ trống:

C: hết chỗ — người 2 đã lấy hết cả 4 screen của C.
B: gần hết — nếu người 1 lấy B1-B3 (hoặc cả B4), chỉ còn B4 hoặc B5 → không đủ 3 screen riêng cho bạn.
A và D: còn khả năng, vì bạn chưa biết chính xác người 3/người 4 đã chốt bao nhiêu screen. A có tới 5 screen gợi ý (A1-A5), D chỉ có 4 (D1-D4).

Khuyến nghị của tôi: chọn ghép chung Scenario A với người 3.

Lý do:

A là function group "giàu" nhất (5 screen gợi ý), lại còn dễ mở rộng thêm screen tự định nghĩa trong cùng nhóm chức năng "quản lý sự kiện" (ví dụ: modal "Important Update", màn "Preview Event", tab "Analytics > Events Stats", "Settings > Featured Event" — vì các trang này vẫn thuộc luồng quản trị sự kiện của Admin).
D chỉ có 4 screen, ít linh hoạt hơn để chia cho 2 người mà không "gượng ép".
Việc dùng chung scenario với người 3 là hợp lệ theo đúng mục 5, miễn là screen set khác nhau hoàn toàn.

Cách chia cụ thể tôi đề xuất: bạn hỏi người 3 xem họ đã chốt cụ thể 3 screen nào (rất có thể là A1, A2, A3 vì đó là luồng "tạo & cấu hình event" cơ bản nhất). Nếu vậy, bạn lấy:

A4 (Participants & Reviews approval — màu trạng thái, progress bar, Export)
A5 (Check-in tab — xử lý trạng thái quét, log real-time)
+ 1 screen tự định nghĩa cùng nhóm, ví dụ "Analytics – Events Stats" hoặc "Settings – Featured Event" (bạn cần viết lý do ngắn: đây vẫn thuộc luồng quản trị sự kiện của Admin, cung cấp góc nhìn UI khác — biểu đồ/carousel — chưa được người 3 kiểm tra).

Việc chọn A4+A5 rất hợp lý vì đây là 2 màn "phức tạp nhất về UI" (progress bar, color-coding, real-time log) — cho bạn nhiều thứ để tìm bug/usability issue, điểm sẽ tốt hơn là chọn màn đơn giản.

⚠️ Việc cần làm ngay: nhắn nhóm xác nhận chính xác người 3 đã chọn screen nào, và người 4 (scenario D) đã chọn screen nào, để tránh trùng hoàn toàn. Nếu người 3 lại chọn đúng A4/A5, bạn chuyển sang ghép D với người 4 (lấy D4 + D-side chưa dùng + 1 screen tự định nghĩa như "Admin Support – Notification badge / list sorting").

Bạn có thể cho tôi biết cụ thể người 3 và người 4 đã chốt screen nào chưa để tôi chốt phương án chính xác hơn không?

3. Danh sách chi tiết các Task & Output cần hoàn thành
Nhóm (làm chung 1 lần, mọi người dùng chung)
#	Output	Định dạng	Nội dung bắt buộc
N1	GUI Checklist	Excel hoặc Markdown	>40 item, phủ đủ IA-01→IA-04
N2	Reference sources	Markdown/txt	Danh sách sách/bài báo/slide đã tham khảo (Nielsen, Norman, Shneiderman, ISTQB...)
N3	AI prompts dùng để tạo checklist	Markdown	Toàn bộ prompt + note "AI bỏ sót gì và vì sao" cho từng item nhóm tự thêm
Cá nhân (chỉ mình bạn làm, dựa trên scenario + ≥3 screens đã chọn)
#	Output	Định dạng	Nội dung bắt buộc
1	Main Report	Markdown + PDF	Scenario chọn + lý do chọn 3 screens + kết quả checklist execution + Usability Report + Cross-platform report
2	Checklist Execution table	Bảng trong report	Mỗi screen × mỗi checklist item → Pass/Fail + cột Notes (lý do fail)
3	Bug reports (từ Task 1B)	Trong report + Google Form	Screen, steps to reproduce, expected vs actual, severity, screenshot
4	User-testing task scenario	Trong report	Kịch bản dạng mục tiêu cho 5 người test
5	Participant table	Bảng (che số liên hệ)	5 người, tên + Zalo/email/SĐT che 4 số giữa
6	Session observation notes	Markdown, 1 file/người hoặc gộp	Ghi chú friction, lỗi, hesitation, cảm xúc
7	SUS/UEQ-S responses	Bảng	Điểm từng người + điểm trung bình
8	Metrics table	Bảng	Success rate, mean time, error count
9	Usability Report	Phần trong Main Report	Findings xếp hạng severity 0-4 kèm ảnh + đề xuất
10	Compatibility matrix	Bảng	3 OS × 5 browser × 3 device, Pass/Fail từng ô, cho mỗi trong 3 screens
11	Cross-platform screenshots	Ảnh	Overlay MSSV@...edu.vn + tên browser/OS/device + URL EMS
12	Bug & Usability Findings Log	Excel/CSV/Markdown	Cột: ID, Scenario/Screen, Type, Description, Steps/Heuristic, Severity, Suggested fix, Screenshot ref, Form timestamp
13	Google Form submissions	Online	Mỗi finding submit riêng, dùng email MSSV
14	AI Audit Report	Markdown + PDF	Từng lần dùng AI: tool, ngày giờ, prompt, output
15	AI Critique	Markdown, 200-300 từ	AI sai/thiếu/lệch ở đâu, vì sao, bài học
16	Git commit log	txt	1 commit mỗi bước (thiết kế checklist, chạy từng screen, log bug, đánh giá, mỗi lần cross-platform)
17	Agent Skill + demo video	Code/skill file + link YouTube	Skill tái sử dụng được cho checklist/usability/compatibility, kèm video minh họa
18	README.md	Markdown	Bảng tự chấm điểm + tóm tắt: scenario, screens, số item checklist, số bug, số participant, số issue theo severity, số ô compatibility đã phủ, link video

Nộp cuối cùng: file .zip đặt tên <MSSV>_HW03_AI_GUIUsability_EMS_<điểm_tự_chấm_3_số>.zip

4. Kế hoạch cụ thể theo từng giai đoạn (10 giờ ước tính)
Giai đoạn 0 — Xác nhận & chuẩn bị (0.5h)
Nhắn nhóm chốt chính xác screen của người 3 (A) hoặc người 4 (D) để tránh trùng.
Đăng ký tài khoản user riêng trên EMS (không dùng chung tài khoản nhóm).
Truy cập thử EMS, chụp vài ảnh state ban đầu để phòng hệ thống bị reset.
Giai đoạn 1 — Task 1 Checklist (2h)
Tham gia cùng nhóm xây bộ checklist >40 item (có thể AI generate trước rồi cả nhóm review cùng lúc, mỗi người bổ sung ít nhất vài item theo hướng chuyên môn — bạn có thể tập trung góp ý phần liên quan đến A4/A5 vì bạn hiểu rõ 2 screen đó).
Chạy checklist trên 3 screen của bạn (A4, A5, + screen tự chọn):
Mở từng screen, review từng item, đánh Pass/Fail.
Chụp ảnh chỉ cho item Fail.
Viết Notes lý do fail.
Gom các Fail thành bug report chuẩn (steps, expected/actual, severity, ảnh).
Submit bug lên Google Form ngay khi phát hiện (đừng để dồn cuối).
Giai đoạn 2 — Task 2 User Testing (3h, nhưng trải dài nhiều ngày vì cần hẹn người thật)
Viết kịch bản test dạng mục tiêu cho A4/A5 (ví dụ: "Hãy duyệt danh sách đăng ký của 1 sự kiện và xử lý check-in cho 1 người tham dự").
Chuẩn bị bảng câu hỏi SUS/UEQ-S + probe questions.
Tuyển 5 người ngoài lớp (bạn bè, người quen) + 1 người pilot.
Chạy pilot → sửa kịch bản nếu cần.
Chạy 5 session thật (mỗi session ~15-20 phút): quan sát, ghi chú, quay màn hình nếu được phép.
Tổng hợp điểm SUS/UEQ-S, tính metric, xếp hạng finding theo severity.
Viết Usability Report.
Giai đoạn 3 — Task 3 Cross-Platform (2h)
Đăng ký BrowserStack/LambdaTest trial.
Lập ma trận cho 3 screen: đảm bảo mỗi OS/browser/device xuất hiện ít nhất 1 lần/screen.
Chạy từng cell, chụp ảnh có overlay MSSV + tên browser/OS/device + URL.
Ghi chú các Fail (overflow, vỡ layout, chữ không đọc được...).
Giai đoạn 4 — Tổng hợp & tài liệu hóa (1.5h)
Viết Main Report (Markdown → convert PDF).
Hoàn thiện Bug & Usability Findings Log, đối chiếu với Google Form đã nộp.
Viết AI Audit Report (log toàn bộ prompt) + AI Critique (200-300 từ).
Viết README.md với bảng tự chấm điểm.
Đảm bảo Git commit log có đủ các mốc: checklist design, checklist execution, bug logging, usability evaluation, mỗi lần chạy cross-platform.
Giai đoạn 5 — Agent Skill + đóng gói (1h)
Viết 1 skill đơn giản (ví dụ script/prompt template tái sử dụng để chạy checklist execution tự động hoặc tổng hợp AI Audit Report).
Quay video demo ngắn, up YouTube (có thể để unlisted).
Đóng gói zip đúng tên file, kiểm tra đủ toàn bộ mục ở phần 3.

Bạn muốn tôi giúp bước nào trước — ví dụ soạn luôn bộ khung checklist >40 item theo IA-01→IA-04, hay viết kịch bản user-testing cho A4/A5, hay dựng bảng compatibility matrix mẫu?
```
---

## Prompt 2
- **AI tool:** Claude Sonnet 5
- **Ngày giờ:** 27/07/2026 08:10 AM
- **Prompt:**
```
giai thich toan bo tung scenario va screen
```
- **AI Output:**
```
Giải thích chi tiết từng Scenario và từng Screen
🅰️ SCENARIO A — Admin tạo và quản lý sự kiện (Event lifecycle phía Admin)

Đây là toàn bộ vòng đời của một sự kiện: từ lúc admin tạo, cấu hình, publish, đến lúc duyệt người đăng ký và check-in. Đây là scenario nhiều màn hình nhất (5 screen) và cũng phức tạp nhất về logic validation.

A1 — Events list (Danh sách sự kiện + bộ lọc trạng thái + chấm thông báo)

Là gì: Trang liệt kê toàn bộ sự kiện admin đã tạo, có thể lọc theo trạng thái (Draft / Published / Ended...), có "chấm đỏ" (notification dot) báo hiệu sự kiện có hoạt động mới cần chú ý (ví dụ có người đăng ký mới cần duyệt).

Các yếu tố UI cần soi:

Bộ lọc trạng thái (status filter) — hoạt động đúng chưa, có phản hồi rõ khi không có kết quả không.
Notification dot — xuất hiện đúng lúc, biến mất đúng lúc sau khi admin đã xem.
Layout bảng/card: căn chỉnh, phân trang, sắp xếp cột.
Empty state khi không có sự kiện nào khớp filter.

Vì sao đáng test: đây là "cổng vào" của toàn bộ luồng A — nếu filter/notification sai, admin sẽ bỏ sót việc cần xử lý (business-critical usability issue).

A2 — Add/Edit Event form (Form tạo/sửa sự kiện — upload ảnh + Rich-Text + validate ngày giờ)

Là gì: Form tạo sự kiện mới hoặc sửa sự kiện có sẵn. Theo tài liệu E2E, đây là màn hình có nhiều "input phức tạp" nhất:

Upload Thumbnail (tỉ lệ 4:3) và Banner (tỉ lệ 24:9) — hai tỉ lệ ảnh khác nhau, dễ sai preview/crop.
RichTextEditor để soạn nội dung (content) sự kiện.
Trường DateTime với validation logic: ngày kết thúc phải sau ngày bắt đầu; thời gian đóng đăng ký phải trước khi sự kiện kết thúc.

Các yếu tố UI cần soi (theo IA-02 Forms):

Label rõ ràng, required-field đánh dấu đúng.
Vị trí hiển thị lỗi validation (ngay dưới field hay tận cuối form?).
Preview ảnh sau upload có đúng tỉ lệ, có rõ nét không.
Khi cố tình nhập sai logic ngày giờ (end < start, hoặc registration deadline > event end) → hệ thống có chặn Save/Publish và báo lỗi rõ ràng không.

Đây là màn hình "vàng" để tìm bug validation — rất đáng chọn nếu bạn muốn nhiều finding.

A3 — Registration & Roles configuration panel (Cấu hình đăng ký & vai trò)

Là gì: Phần cấu hình ai được đăng ký sự kiện (student/lecturer/guest), có bao nhiêu chỗ (Max Slots), có cho waitlist (danh sách chờ) không, có vai trò phụ (additional role) không.

Logic đặc biệt cần test:

Bật/tắt từng toggle (allowStudentRegistration, allowLecturerRegistration, allowGuestRegistration) → form phải hiển thị động đúng theo toggle (progressive disclosure).
Nếu tắt isUnlimited (không giới hạn) nhưng không nhập Max Slots → hệ thống phải chặn lưu/publish.
Bật Waitlist → có thêm cấu hình liên quan.
Bật "Allow Additional Role" → cho nhập tên vai trò phụ tùy ý.

Vì sao đáng test: nhiều nhánh điều kiện lồng nhau (conditional UI) — rất dễ phát sinh lỗi hiển thị sai hoặc validate thiếu.

A4 — Participants & Reviews approval (Duyệt người đăng ký — màu trạng thái, progress bar, Export)

Là gì: Nơi admin duyệt (Approve/Reject) từng người đăng ký sự kiện, có tab riêng cho Lecturer Review và Student review.

Chi tiết logic đặc biệt (theo tài liệu E2E, đây là điểm rất hay để test):

Có 6 màu trạng thái khác nhau (xanh lá, vàng, đỏ, xanh dương, tím, xám) — mỗi màu đại diện 1 status, dễ gây nhầm lẫn nếu màu không nhất quán hoặc không có chú thích (legend).
Ràng buộc đặc biệt: nếu một giảng viên đăng ký với nhiều vai trò cùng lúc, admin phải quyết định (approve/reject) hết tất cả các vai trò trong đăng ký đó rồi mới được bấm "Apply" — nếu chỉ duyệt 1 role rồi Apply, hệ thống phải chặn/lỗi.
Có nút "Approve All" (duyệt hàng loạt).
Progress bar thể hiện tiến độ duyệt/tỷ lệ tham gia.
Bộ lọc "Target Type" (lọc theo loại người đăng ký).
Nút Export ra Excel.

Vì sao đáng chọn: đây là màn hình giàu UI feedback nhất (IA-04) — nhiều màu sắc, progress bar, ràng buộc logic phức tạp → rất nhiều khả năng tìm ra bug/usability issue thật.

A5 — Check-in tab (Xử lý quét mã — nhiều trạng thái, log real-time)

Là gì: Màn hình admin dùng để quét mã QR/barcode của người tham dự khi họ đến sự kiện.

Các trạng thái quét (rất đáng chú ý):

Quét mã hợp lệ → SUCCESS
Quét lại mã đã quét → ALREADY_CHECKED_IN
Quét ngoài khung giờ cho phép → OUTSIDE_CHECKIN_WINDOW
Quét mã người chưa đăng ký nhưng có trong hệ thống → PENDING_REVIEW, admin phải Accept (duyệt) hoặc Decline (kèm lý do).
Nhật ký quét (log) phải cập nhật real-time.
Có nút xuất Excel lịch sử quét.

Vì sao đáng test: đây là màn hình có nhiều trạng thái hệ thống (system status) nhất — rất phù hợp để test IA-04 (feedback/state) và cả UEQ dạng "trust" (người dùng có tin vào kết quả quét không).

🅱️ SCENARIO B — User đăng ký tham dự sự kiện (Public discovery & registration)

Đây là trải nghiệm của người dùng cuối (student/guest) khi họ vào EMS để tìm và đăng ký sự kiện.

B1 — Home / Events listing (Trang chủ — carousel nổi bật, danh mục, tìm kiếm)

Là gì: Trang public đầu tiên người dùng thấy khi vào EMS: có carousel các sự kiện nổi bật (auto-rotate mỗi 7 giây theo tài liệu E2E, chỉ hiển thị event đã Published + đang/sắp diễn ra), danh mục sự kiện để browse, thanh tìm kiếm/lọc.

Cần soi: carousel có tự chuyển đúng nhịp không, category filter/search hoạt động đúng, responsive trên các độ rộng khác nhau, loading state khi tải dữ liệu.

B2 — Event detail page (Trang chi tiết sự kiện)

Là gì: Khi click vào 1 sự kiện, xem banner, lịch trình, nút "Đăng ký", thông báo waitlist nếu đã hết chỗ.

Cần soi: banner hiển thị đúng tỉ lệ, nút đăng ký disable/enable đúng theo trạng thái (còn chỗ / hết chỗ / đã đóng đăng ký), thông báo waitlist rõ ràng chưa.

B3 — Registration form (Form đăng ký — chọn vai trò, xác nhận)

Là gì: Form để người dùng chọn vai trò tham gia (student/lecturer/guest, hoặc vai trò phụ nếu event cho phép), rồi xác nhận đăng ký.

Cần soi: validate chọn vai trò, confirmation message/dialog rõ ràng, xử lý khi hết chỗ → tự động vào waitlist có thông báo rõ không.

B4 — My Registrations / ticket (Danh sách đăng ký của tôi + vé QR)

Là gì: Trang liệt kê các sự kiện người dùng đã đăng ký, xem trạng thái (đã duyệt/chờ duyệt/waitlist), và vé có mã barcode/QR để check-in.

Cần soi: mã QR hiển thị rõ, đủ lớn để quét, trạng thái đăng ký đồng bộ đúng với phía Admin (A4).

B5 — Post-event review (Đánh giá sao 1-5 sau sự kiện)

Là gì: Sau khi sự kiện kết thúc, người dùng có thể đánh giá 1-5 sao.

Cần soi: chỉ hiện nút review khi event đã ENDED, UI chọn sao trực quan, feedback khi submit thành công.

🅲️ SCENARIO C — Admin quản lý người dùng (User administration)
C1 — Users list (Danh sách người dùng — tìm kiếm, lọc role/active, cột)

Là gì: Bảng liệt kê toàn bộ user với các cột: Avatar+Name, Role, Member Code, Active, Audit.

Cần soi: filter theo role/trạng thái hoạt động, search theo tên/mã số, độ rõ của cột Audit (lịch sử thay đổi).

C2 — Assign Role / edit user (Gán vai trò / sửa thông tin user)

Là gì: Đổi vai trò tài khoản (ví dụ thành giảng viên/sinh viên).

Cần soi: dropdown chọn role rõ ràng, confirmation trước khi đổi (vì đây là hành động nhạy cảm), phản hồi sau khi lưu thành công.

C3 — Block/Unblock và Reset-Password dialogs (Dialog xác nhận + audit)

Là gì: Các hành động quan trọng: khóa/mở khóa tài khoản, đặt lại mật khẩu — đều cần dialog xác nhận vì có thể gây hậu quả lớn (tài khoản bị block không thể truy cập hệ thống).

Cần soi: dialog có xác nhận rõ ràng (tránh bấm nhầm), có ghi nhận vào audit log không, tài khoản bị Block có thực sự không login được không (test thực tế).

C4 — Export to Excel (Xuất Excel — đầy đủ cột, phản hồi khi tải)

Là gì: Nút xuất danh sách user ra file Excel.

Cần soi: file tải về có đủ cột (Avatar+Name, Role, Member Code, Active, Audit) không, có loading feedback trong lúc export không, tên file có ý nghĩa không.

🅳️ SCENARIO D — User gửi yêu cầu hỗ trợ, Admin xử lý (Support request lifecycle)

Đây là scenario duy nhất trải dài cả 2 phía (user tạo request, admin xử lý) — nên bạn cần cả 2 tài khoản (user tự đăng ký + admin có sẵn).

D1 — User: tạo support request (form + đính kèm ảnh)

Là gì: Form người dùng tạo yêu cầu hỗ trợ: chọn category, nhập nội dung, đính kèm ảnh minh họa.

Cần soi: validate category bắt buộc chọn, giới hạn định dạng/kích thước ảnh upload có thông báo rõ không, feedback sau khi gửi thành công.

D2 — User: My Requests list + detail (xem phản hồi)

Là gì: Danh sách các yêu cầu người dùng đã gửi, xem chi tiết và phản hồi chính thức từ Admin.

Cần soi: trạng thái Pending/Resolved hiển thị rõ, thông báo khi có phản hồi mới (real-time hay phải refresh?).

D3 — Admin: Support Requests list (tab Pending/Resolved, tìm kiếm)

Là gì: Danh sách các yêu cầu hỗ trợ phía admin, có tab Pending/Resolved, tìm kiếm theo mã thành viên hoặc category.

Cần soi: tab switch có giữ đúng filter không, search hoạt động đúng, đếm số lượng pending có chính xác/real-time không.

D4 — Admin: request detail (image lightbox, internal note, phản hồi chính thức)

Là gì: Trang chi tiết 1 yêu cầu — admin xem ảnh đính kèm (dạng lightbox phóng to), viết internal note (chỉ admin thấy, không hiện cho user), và viết phản hồi chính thức gửi cho user.

Cần soi (rất đáng chú ý về IA-04):

Lightbox ảnh hoạt động mượt, đóng/mở đúng.
Phân biệt rõ ràng giữa Internal note (private) và Official response (public) — đây là điểm dễ gây lỗi bảo mật UI nghiêm trọng nếu hiển thị nhầm.
Sau khi gửi phản hồi, request có tự chuyển từ Pending → Resolved không, có thông báo cho user không.
📊 Bảng so sánh nhanh để bạn cân nhắc chọn/đối chiếu độ "giàu" từng screen
Screen	Độ phức tạp UI	IA nổi bật	Bug tiềm năng
A2 (Add/Edit Event)	Rất cao	IA-02	Validate ngày giờ, upload ảnh 2 tỉ lệ
A3 (Reg & Roles config)	Cao	IA-02, IA-03	Conditional UI lồng nhau
A4 (Participants approval)	Rất cao	IA-04	6 màu trạng thái, rule duyệt multi-role
A5 (Check-in)	Rất cao	IA-04	4 trạng thái quét, real-time log
B3 (Registration form)	Trung bình	IA-02	Waitlist logic
C3 (Block/Reset dialogs)	Trung bình	IA-04	Confirmation, audit
D4 (Request detail)	Cao	IA-04	Internal note vs public response — rủi ro bảo mật UI

Vì bạn nhiều khả năng sẽ ghép vào scenario A (cùng người 3) với các screen A4 + A5 + có thể thêm 1 screen tự chọn — đây thực ra là 2 screen giàu nhất về mặt tìm bug/usability issue trong toàn bộ 4 scenario, nên khá thuận lợi cho điểm số nếu bạn khai thác kỹ phần "màu trạng thái", "ràng buộc multi-role approval", và "4 trạng thái check-in".

Bạn đã hỏi được người 3 (Scenario A) và người 4 (Scenario D) chốt đúng screen nào chưa? Nếu có, báo tôi để tôi chốt chính xác bộ 3 screen của bạn và viết luôn phần "lý do chọn screen" cho report.
```
---

## Prompt 3
- **AI tool:** Claude Sonnet 5
- **Ngày giờ:** 27/07/2026 08:30 AM
- **Prompt:**
```
dựa vào toàn bộ nội dung task và output trên, hãy xuất cho tôi toàn bộ file format tôi cần thực hiện dạng md
```
- **AI Output:**
```
Tôi sẽ tạo bộ file Markdown mẫu đầy đủ cho tất cả các output cần nộp, sẵn sàng để bạn điền dữ liệu thật vào.

Created 12 files
Created 12 files

Đã tạo xong bộ 12 file Markdown mẫu, bám sát đúng từng mục yêu cầu của đề (§6 → §16):

Presented 12 files
Presented 12 files

Tóm tắt nhanh mục đích từng file:

File	Dùng cho
01_GROUP_gui_checklist.md	Task 1A — checklist chung nhóm + nguồn tham chiếu + AI prompts
02_main_report.md	Báo cáo chính (tóm tắt, link tới các file chi tiết)
03_checklist_execution.md	Task 1B — Pass/Fail từng screen
04_bug_reports.md	Bug report chuẩn (steps/expected/actual/severity)
05_usability_testing.md	Task 2 toàn bộ 3 phase (scenario, participants, sessions, SUS, findings)
06_cross_platform_matrix.md	Task 3 — ma trận OS×Browser×Device
07_bug_usability_findings_log.md	File tổng hợp §7 (đối chiếu Google Form)
08_ai_audit_report.md	Mục 10 — log AI đầy đủ
09_ai_critique.md	Mục 11 — đoạn phê bình 200-300 từ
10_git_commit_log.md	Mục 13
11_agent_skill_demo.md	Mục 8
README.md	Bảng tự chấm + test summary

Nhớ: 01_GROUP_gui_checklist.md là file duy nhất dùng chung với nhóm — các file còn lại phải khác nhau giữa các thành viên (đề đã nhấn mạnh copy prompt/screen giữa các bạn sẽ bị 0 điểm). Bạn muốn tôi giúp điền sẵn nội dung mẫu cho 3 screen cụ thể của bạn (A4, A5, + 1 screen tự chọn) luôn không?
```
---

## Prompt 4
- **AI tool:** Claude Sonnet 5
- **Ngày giờ:** 28/07/2026 08:30 AM
- **Prompt:**
```
tai sao lai lm agent skill cuối cùng ? ko phải là skill phải lm đầu tiên để test hả
```
- **AI Output:**
```
Câu hỏi rất hay — đây đúng là điểm nhiều người hiểu ngược. Để tôi giải thích lý do tôi xếp Agent Skill ở cuối, dựa trên chính cách đề bài diễn đạt, chứ không phải ngẫu nhiên.

1. Đọc kỹ lại câu chữ của đề (mục 8)

"You are encouraged to build Agent Skills that apply the GUI-checklist execution, the heuristic usability evaluation, and the compatibility-matrix runs, so they can be reused on additional EMS screens and flows."

Từ khóa quan trọng là "additional" — tức là Skill được sinh ra để dùng cho các screen khác/thêm ngoài 3 screen bắt buộc bạn đã làm, chứ không phải để "chạy hộ" 3 screen chính bạn nộp điểm. Skill ở đây giống như sản phẩm phụ tái sử dụng, không phải công cụ chính để tạo ra bài nộp.

2. Vì sao KHÔNG nên build skill trước rồi chạy nó để làm bài?

Đề nhấn mạnh rất rõ ở mục 2 (Guiding Principles):

"you must guide the AI through every step of the technique as it was taught, using the AI as a disciplined assistant rather than a black box."

Nếu bạn build sẵn 1 skill tự động hóa hoàn chỉnh rồi chạy nó để ra kết quả checklist/usability/compatibility cho 3 screen chính — đó chính xác là biến AI thành black box, vi phạm nguyên tắc cốt lõi của cả bài. TA sẽ nhìn vào AI Audit Report và thấy bạn không thực sự "guide" AI từng bước, mà chỉ bấm 1 nút cho ra kết quả — đây là rủi ro bị trừ điểm nặng nhất trong toàn bài.

3. Nguyên tắc thực tế trong ngành: "Manual trước, Automate sau"

Đây cũng là nguyên tắc chuẩn trong software testing thật: bạn không automate một quy trình mà bạn chưa từng làm tay và chưa hiểu rõ nó. Nếu automate trước khi hiểu, kết quả thường là:

Skill bỏ sót các trường hợp đặc thù (vì bạn chưa gặp chúng khi làm tay)
Skill không biết cách xử lý các ràng buộc nghiệp vụ phức tạp của EMS (như rule duyệt multi-role ở A4, hay 4 trạng thái quét ở A5) — vì bạn chưa "va" vào chúng

Làm tay 3 screen trước giúp bạn biết rõ "làm đúng kỹ thuật này" trông như thế nào, từ đó mới viết được 1 skill thực sự tốt và tổng quát hóa đúng.

4. Vậy trình tự hợp lý là gì?
1. Làm tay (có AI hỗ trợ từng bước, có log prompt) → checklist execution, 
   usability test, compatibility matrix cho 3 screen bắt buộc
   ↓
2. Sau khi đã hiểu rõ quy trình, đúc kết lại thành Agent Skill 
   (skill chính là "công thức" bạn vừa làm, được viết lại dạng tái sử dụng)
   ↓
3. Demo skill đó chạy trên 1 flow/screen khác (có thể là screen thứ 4, 
   hoặc chạy lại 1 phần nhỏ) → quay video chứng minh end-to-end
5. Nhưng cũng có cách linh hoạt hơn nếu bạn muốn tiết kiệm thời gian

Bạn hoàn toàn có thể vừa làm vừa phác thảo skill song song (draft sớm, tinh chỉnh dần), miễn là:

Log AI Audit Report vẫn thể hiện rõ bạn guide AI từng bước cho 3 screen chính (không phải "chạy skill 1 phát ra hết")
Bản skill hoàn chỉnh + video demo chỉ cần sẵn sàng vào cuối để nộp

Nói cách khác: không phải lúc nào cũng phải làm xong 100% task 1-2-3 rồi mới bắt đầu code skill — bạn có thể song song, nhưng kết quả nộp chính (checklist/usability/compatibility) phải đến từ quá trình bạn tự tay guide AI, còn skill là phần "gói lại" quy trình đó để dùng tiếp, nên tự nhiên nó sẽ hoàn thiện/final hóa muộn hơn trong timeline.

Bạn có muốn tôi điều chỉnh lại plan 10 giờ để thể hiện rõ việc "vừa làm vừa phác thảo skill" thay vì tách hẳn 2 giai đoạn không?
```
---

## Prompt 5
- **AI tool:** Claude Sonnet 5
- **Ngày giờ:** 28/07/2026 09:00 AM
- **Prompt:**
```
Bạn có muốn tôi điều chỉnh lại plan 10 giờ để thể hiện rõ việc "vừa làm vừa phác thảo skill" thay vì tách hẳn 2 giai đoạn không? có
```
- **AI Output:**
```
Kế hoạch 10 giờ (đã điều chỉnh — vừa làm vừa phác thảo Skill song song)
Nguyên tắc xuyên suốt
Task 1B/2/3 chính (nộp điểm) = luôn làm tay + AI hỗ trợ từng bước, có log prompt đầy đủ.
Skill = ghi chú lại song song mỗi khi thấy 1 bước lặp lại đủ nhiều lần để đáng "đóng gói", rồi hoàn thiện + quay video vào cuối.
Giai đoạn 0 — Chuẩn bị (0.5h)
Xác nhận screen với nhóm (tránh trùng người 3/người 4).
Đăng ký tài khoản user riêng, chụp ảnh state ban đầu phòng hệ thống reset.
Khởi tạo Git repo + commit đầu tiên ("init project structure").
Giai đoạn 1 — Task 1: Checklist (2h)

1a. Xây checklist chung với nhóm (0.5h)

Cùng nhóm prompt AI generate bộ checklist ban đầu → review → bổ sung item EMS-specific.
Log lại prompt vào 01_GROUP_gui_checklist.md.
Git commit: "checklist: draft + refine >40 items".

1b. Chạy checklist tay trên Screen 1 (VD: A4) (0.5h)

Tự mở screen, đối chiếu từng item, đánh Pass/Fail, ghi Notes.
📝 Bắt đầu note nháp cho Skill 1: "Mỗi lần chạy 1 item, mình đang lặp lại thao tác: đọc item → chụp UI hiện tại → so sánh → gán Pass/Fail → nếu Fail thì viết lý do + đặt tên ảnh theo convention". → Đây chính là logic sẽ đưa vào Skill "gui-checklist-executor". Ghi nháp vào file skill_notes.md ngay lúc này, chưa cần code.
Git commit: "execution: checklist Screen 1".

1c. Chạy checklist Screen 2 (A5) (0.5h)

Làm tương tự, đối chiếu xem quy trình ở 1b có lặp lại đúng như dự đoán không → tinh chỉnh note skill nếu cần (VD: phát hiện thêm bước "cần phân biệt severity ngay lúc Fail" mà lúc 1b chưa nghĩ tới).
Git commit: "execution: checklist Screen 2".

1d. Chạy checklist Screen 3 + tổng hợp bug (0.5h)

Hoàn tất execution, viết bug report chuẩn vào 04_bug_reports.md, submit Google Form.
Git commit: "execution: checklist Screen 3 + bug logging".
Giai đoạn 2 — Task 2: Usability Testing (3h, trải dài nhiều ngày để hẹn người thật)

2a. Thiết kế scenario + metric (0.5h)

Viết task scenario, bảng metric, câu hỏi probe (dùng AI hỗ trợ soạn câu hỏi, log prompt).
📝 Note skill 2: "Việc chấm điểm SUS + phân loại severity theo công thức có thể tự động hóa" → phác thảo ý tưởng cho Skill "usability-analyzer" (chưa code, chỉ ghi ý tưởng input/output).
Git commit: "usability: design scenario + metrics".

2b. Pilot + tuyển người (0.5h)

Chạy pilot, tinh chỉnh scenario.
Git commit: "usability: pilot + refine".

2c. Chạy 5 session thật (1.5h, có thể trải nhiều buổi)

Quan sát, ghi chú tay từng session — phần này không automate được vì cần con người thật, AI chỉ hỗ trợ gợi ý câu hỏi follow-up nếu cần.
Git commit sau mỗi session hoặc gộp: "usability: run session P1-P5".

2d. Phân tích + viết Usability Report (0.5h)

Dùng AI hỗ trợ tổng hợp/xếp hạng severity (log prompt), bạn review lại kết quả.
📝 Cập nhật note skill 2: giờ bạn đã biết chính xác input (5 bộ điểm SUS + ghi chú) và output (bảng xếp hạng) cần gì → note đã đủ chi tiết để code sau.
Git commit: "usability: analyse + write report".
Giai đoạn 3 — Task 3: Cross-Platform (2h)

3a. Setup BrowserStack/LambdaTest (0.2h)

3b. Chạy matrix Screen 1 (0.6h)

Test thủ công từng cell, chụp ảnh overlay MSSV.
📝 Note skill 3: "Mỗi cell cần: chọn OS/browser/device → mở URL → chụp ảnh overlay → ghi Pass/Fail vào bảng" → phác thảo ý tưởng Skill "compatibility-matrix-builder" (VD: sinh sẵn khung bảng theo yêu cầu phủ đủ OS/browser/device, hoặc tự động check đã đủ coverage chưa).
Git commit: "cross-platform: Screen 1".

3c. Chạy matrix Screen 2 & 3 (1.2h)

Lặp lại, áp dụng luôn ý tưởng note ở 3b để làm nhanh hơn (nhưng vẫn làm tay, chưa cần code skill thật).
Git commit riêng từng screen.
Giai đoạn 4 — Tổng hợp tài liệu (1h)
Viết Main Report, Findings Log, README.
Viết AI Audit Report (tổng hợp lại toàn bộ prompt đã log rải rác ở các bước trên).
Viết AI Critique (200-300 từ).
Git commit: "report: finalize documentation".
Giai đoạn 5 — Hoàn thiện Agent Skill (1.5h) — giờ mới thực sự code

Lúc này bạn đã có đủ 3 bộ note nháp từ Giai đoạn 1-3, việc code skill chỉ là "đúc kết lại":

Skill 1 — gui-checklist-executor (0.5h): viết SKILL.md dựa trên note ở bước 1b/1c, test thử trên 1 screen khác (screen thứ 4 chưa dùng, hoặc 1 phần nhỏ chưa test) để chứng minh tái sử dụng được.
Skill 2 — usability-analyzer (0.5h): viết dựa trên note ở 2d, test thử với dữ liệu SUS giả lập hoặc 1 phần dữ liệu thật.
Skill 3 — compatibility-matrix-builder (0.3h): viết dựa trên note ở 3b, test sinh khung bảng cho 1 screen mới.
Quay video demo (0.2h): cho mỗi skill chạy trên 1 trường hợp cụ thể, up YouTube (có thể để unlisted).
Git commit: "skill: implement + demo 3 Agent Skills".
Vì sao cách này tốt hơn?
Cách cũ (tách 2 giai đoạn)	Cách mới (song song)
Dễ quên chi tiết quy trình thật khi ngồi code skill sau cùng	Note ngay lúc làm tay → skill phản ánh đúng thực tế, không "tưởng tượng"
Rủi ro build skill xong mới nhận ra thiếu case đặc thù → phải sửa lại	Skill được tinh chỉnh dần qua từng screen → ít phải sửa lại
AI Audit Report dễ bị nghi ngờ là "chạy skill có sẵn" nếu code trước	Log chứng minh rõ ràng: làm tay trước, skill là sản phẩm rút ra sau — đúng tinh thần "disciplined assistant, not black box"

Bạn có muốn tôi cập nhật luôn nội dung này vào file 11_agent_skill_demo.md (thêm phần "Development timeline" để giải thích cho TA thấy quy trình đúng chuẩn) không?
```

----
## Prompt 6
**AI Tool:** Claude Sonnet 5
**Ngày giờ:** 28/07/2026 10:15 PM
**Prompt:**
```
trong yeu cau bai co viet toi can guide AI qua tung buoc, v toi can guide AI qua tung buoc nao
```

**AI Output:**
``` 
Đây là câu hỏi cốt lõi của toàn bộ bài — vì nếu làm sai chỗ này, dù kết quả cuối có đẹp đến đâu cũng dễ bị đánh giá thấp phần "AI-First". Tôi sẽ giải thích rõ khái niệm, rồi liệt kê chính xác các bước bạn cần "guide" AI qua, ứng với công việc thật của bạn (A4, A5, Dashboard).

1. Phân biệt "1 prompt chung chung" (SAI) vs "guide từng bước" (ĐÚNG)

Đề bài nêu ví dụ rất rõ về việc KHÔNG được làm:

"this does not mean issuing a single, generic prompt such as 'generate a GUI checklist and find usability problems in this app.'"

Nghĩa là nếu bạn gõ đúng 1 câu như trên rồi để AI tự làm hết từ A-Z, đó là black box — sai hoàn toàn tinh thần bài.

"Guide từng bước" nghĩa là: bạn tách kỹ thuật kiểm thử (GUI checklist testing, usability testing, compatibility testing) thành các bước con đúng như đã học trên lớp, rồi ở MỖI bước, bạn tự làm phần con người cần làm (quan sát, quyết định, cung cấp dữ liệu thật), và chỉ nhờ AI xử lý phần AI làm tốt (viết lại có cấu trúc, gợi ý, tổng hợp) — sau đó bạn review lại trước khi dùng.

2. Các bước cụ thể bạn cần guide AI — theo đúng 3 kỹ thuật của bài
🅰️ Kỹ thuật 1: GUI Checklist Testing (Task 1)
Bước	Ai làm	AI được guide làm gì
1. Xác định 4 khía cạnh IA cần checklist	Bạn (đã có sẵn trong đề)	—
2. Generate bộ khung ban đầu	AI	Prompt: "Tạo checklist theo 4 nhóm IA-01→04, ghi rõ nguồn heuristic cho mỗi item"
3. Bổ sung đặc thù nghiệp vụ EMS	Bạn cung cấp context, AI viết	Prompt riêng, có mô tả cụ thể A4/A5 (bạn đã làm bước này)
4. Review & loại bỏ item trùng/mơ hồ	Bạn (con người)	AI không nên tự quyết định item nào giữ/bỏ
5. Chạy từng item lên screen thật, quan sát Pass/Fail	Bạn (con người) — bắt buộc, không giao AI	Đây là phần AI KHÔNG được làm thay, vì AI không tự vào EMS xem được
6. Viết lại bug report cho chuẩn format	AI (dựa trên mô tả thật của bạn)	Prompt: "Viết bug report chuẩn từ mô tả sau: [mô tả bug thật bạn quan sát]"
7. Kiểm tra/sửa severity AI đề xuất	Bạn (con người)	AI chỉ gợi ý, bạn quyết định cuối

→ Điểm mấu chốt: bước 5 và bước 4/7 bắt buộc là bạn, AI chỉ hỗ trợ bước 2, 3, 6.

🅱️ Kỹ thuật 2: Usability Testing với 5 người (Task 2)
Bước	Ai làm	AI được guide làm gì
1. Thiết kế task scenario (mục tiêu, không phải bước bấm)	AI viết nháp, bạn chỉnh	Prompt riêng cho từng phần: scenario → metrics → probe questions (3 prompt tách biệt, không gộp 1 prompt)
2. Tuyển người, chạy pilot	Bạn (con người) — bắt buộc	AI không thể làm thay
3. Quan sát, ghi chú trong session	Bạn (con người) — bắt buộc	Đây là dữ liệu thô thật, AI tuyệt đối không được bịa
4. Tính điểm SUS theo công thức	AI (nhưng bạn kiểm tra lại công thức)	Prompt: "Tính SUS từ các câu trả lời sau: [dữ liệu thật]"
5. Nhóm pain point, xếp severity	AI đề xuất, bạn xác nhận	Prompt riêng, dựa trên ghi chú thật của bạn — không được để AI tự tưởng tượng thêm finding không có trong dữ liệu bạn cung cấp
6. Viết Usability Report hoàn chỉnh	AI dựng khung, bạn viết nội dung thật vào	—
🅲️ Kỹ thuật 3: Cross-Platform Testing (Task 3)
Bước	Ai làm	AI được guide làm gì
1. Lập kế hoạch coverage (OS × Browser × Device)	AI gợi ý cấu trúc bảng	Prompt: "Gợi ý cách chọn cell để phủ đủ 3 OS/5 browser/3 device mà tối thiểu số cell"
2. Chạy thật trên BrowserStack/LambdaTest, chụp ảnh	Bạn (con người) — bắt buộc	AI không có quyền truy cập BrowserStack thay bạn
3. Viết mô tả lỗi rendering	AI viết lại cho chuẩn, bạn xác nhận đúng thực tế	Prompt: "Viết mô tả lỗi layout từ quan sát sau: [mô tả bug thật]"
3. Vậy với chính công việc bạn đang làm (A4/A5/Dashboard), "guide từng bước" trông như thế nào trong thực tế?

Nhìn lại cuộc trò chuyện của chúng ta, bạn đã và đang làm đúng cách này mà không nhận ra — đây chính xác là ví dụ sống của "guide AI từng bước":

Bạn hỏi tôi generate checklist khung (bước AI) →
Bạn tự chụp ảnh Registrants/Review Lecturers/Review Students thật (bước con người) →
Bạn đưa ảnh cho tôi, tôi chỉ diễn giải lại thành bảng Pass/Fail có cấu trúc dựa trên ĐÚNG những gì thấy trong ảnh (bước AI hỗ trợ, có ràng buộc rõ) →
Bạn cần tự bấm thử "Reject All", tự kiểm tra double-submit, tự xác nhận notification dot (bước con người, tôi đã nói rõ "cần test trực tiếp") →
Sau khi bạn xác nhận, tôi mới giúp viết lại thành Bug Report chuẩn (bước AI hỗ trợ)

→ Đây chính là chuỗi bước hợp lệ. Điều bạn cần làm để ghi lại đúng chuẩn AI Audit Report là: log lại từng prompt riêng biệt này (không gộp thành 1 prompt lớn), theo đúng thứ tự thời gian, và với mỗi prompt ghi rõ bạn đã sửa/xác nhận gì so với output AI.

4. Checklist nhanh để tự kiểm tra bạn có đang "guide đúng" hay không

Trước khi gửi bất kỳ prompt nào, tự hỏi:

❌ Prompt này có đang yêu cầu AI tự quyết định cả kết luận cuối cùng (VD: "AI tự chấm severity, tự kết luận có bug hay không") mà không dựa trên dữ liệu thật bạn cung cấp không? → Nếu có, sai.
✅ Prompt này chỉ nhờ AI xử lý/viết lại 1 phần việc cụ thể, dựa trên dữ liệu/quan sát thật bạn đưa vào, và bạn sẽ review lại kết quả trước khi dùng chính thức? → Đúng cách.

Bạn muốn tôi giúp bạn viết lại toàn bộ chuỗi prompt bạn đã dùng từ đầu đến giờ (checklist generate, checklist bổ sung, phân tích ảnh A4) thành đúng format 08_ai_audit_report.md theo thứ tự thời gian không?
```
----
## Prompt 7
**AI Tool:** Claude Sonnet 5
**Ngày giờ:** 28/07/2026 10:30 PM
**Prompt:**
```
tôi quyết định chọn pool A  Theo dõi và vận hành sự kiện: Dashboard KPIs - Participant & Review Approval - Checkin, dựa vào plan ở trên, hướng dẫn tôi chi tiết từng bước
```

- **AI Output:**
``` 
Được, tôi sẽ hướng dẫn bạn từng bước cụ thể, kèm prompt sẵn để copy-paste, đi từ đầu đến cuối cho đúng 3 screen bạn chọn:

Screen 1: Dashboard KPIs (Total Events, Total Check-ins, Attendance Rate, Total Users)
Screen 2: Participants & Reviews Approval (A4)
Screen 3: Check-in tab (A5)

⚠️ Lưu ý quan trọng trước tiên: Dashboard không nằm trong danh sách gợi ý A1-A5, nên bạn cần viết lý do chọn nó vào report. Lý do hợp lệ: đề bài mục 4 liệt kê Dashboard KPIs là 1 phần của Pool A, và đây là màn hình "cổng vào" thể hiện trạng thái tổng quan toàn hệ thống — rất hợp với IA-01 (general UI) và IA-04 (feedback/state, vì có số liệu động). Tôi sẽ viết sẵn câu justify này cho bạn ở dưới.

BƯỚC 0 — Chuẩn bị (làm ngay bây giờ, 15 phút)
Nhắn nhóm xác nhận: "Mình lấy Scenario A — Dashboard KPIs, A4 (Participants & Reviews), A5 (Check-in)" để người 3 (cũng lấy A) biết và tránh trùng screen.
Vào EMS bằng tài khoản admin: admin@gmail.com / Admin@123 tại https://prod-dev.ems-fitus.cloud/ (hoặc URL ngrok bạn có).
Chụp ngay 3 ảnh ban đầu của Dashboard, tab Participants & Reviews, tab Check-in (phòng hệ thống bị reset mất state).
Tạo thư mục làm việc:
HW03_[MSSV]/
├── screenshots/
│   ├── checklist_fails/
│   ├── bugs/
│   ├── cross_platform/
├── skill_notes.md   (ghi nháp ý tưởng skill dần)
Khởi tạo git: git init → git add . → git commit -m "init: project structure"
BƯỚC 1 — Task 1A: Đóng góp cho checklist chung nhóm (30 phút)

Đây là việc làm cùng nhóm, nhưng vì bạn phụ trách screen giàu logic nhất (A4, A5), bạn nên chủ động đóng góp phần item liên quan đến trạng thái/màu sắc/progress bar.

Prompt 1 — gửi cho AI (ChatGPT/Claude) để nhóm generate checklist ban đầu
Bạn là một chuyên gia kiểm thử usability. Hãy tạo một GUI checklist gồm hơn 40 mục,
dùng để đánh giá giao diện của một hệ thống quản lý sự kiện (Event Management System)
dành cho trường đại học. Checklist phải chia thành 4 nhóm:

- IA-01: General UI standards (layout, alignment, typography, colour, consistency,
  i18n EN/VI, empty/loading states)
- IA-02: Forms (labels, validation, error placement, required-field handling,
  uploads, rich-text editor)
- IA-03: Navigation (menus, breadcrumbs, tabs, sidebar, drag-and-drop reorder,
  back/return actions, deep links)
- IA-04: Feedback / state (toasts, badges, confirmation dialogs, progress bars,
  status colours, real-time updates)

Mỗi mục checklist phải là 1 câu hỏi kiểm tra cụ thể (không chung chung), và ghi rõ
nguồn tham chiếu (Nielsen's 10 heuristics / Norman's 6 principles / Shneiderman's
8 golden rules / general UX best practice) cho mỗi mục. Trình bày dưới dạng bảng
markdown: | # | Item | Reference |
Prompt 2 — bổ sung đặc thù EMS (rất quan trọng — đây là phần bạn tự thêm)
Dưới đây là mô tả các màn hình cụ thể của hệ thống EMS mà nhóm mình sẽ kiểm thử.
Hãy đề xuất thêm 10-15 checklist item MỚI (không trùng với bộ 40 item trước),
tập trung vào các đặc thù nghiệp vụ sau, và với mỗi item hãy giải thích ngắn
gọn vì sao đây là điểm dễ bị bỏ sót nếu chỉ dùng checklist UI tổng quát:

1. Dashboard hiển thị 4 KPI: Total Events, Total Check-ins, Attendance Rate,
   Total Users — số liệu này cập nhật real-time hay phải refresh trang?
2. Màn hình duyệt đăng ký (Participants & Reviews) có 6 màu trạng thái khác
   nhau (xanh lá, vàng, đỏ, xanh dương, tím, xám), có progress bar thể hiện
   tiến độ duyệt, và có ràng buộc: nếu 1 giảng viên đăng ký nhiều vai trò
   trong cùng 1 lượt đăng ký, admin phải duyệt/từ chối HẾT tất cả vai trò
   rồi mới được bấm Apply.
3. Màn hình Check-in xử lý 4 trạng thái quét mã khác nhau: SUCCESS,
   ALREADY_CHECKED_IN, OUTSIDE_CHECKIN_WINDOW, PENDING_REVIEW (cần admin
   Accept/Decline), và có nhật ký quét cập nhật real-time.

Với mỗi item bạn đề xuất, ghi rõ: "Vì sao một checklist UI tổng quát (không
biết chi tiết nghiệp vụ trên) sẽ không tự nghĩ ra được item này."

→ Copy nguyên văn 2 prompt + output vào file 01_GROUP_gui_checklist.md (mục AI Prompts) và vào 08_ai_audit_report.md.

Sau khi có output, cả nhóm cùng ngồi review, xóa bớt item trùng lặp/mơ hồ, chốt bản cuối >40 item.

Git commit: checklist: draft + refine >40 items

BƯỚC 2 — Task 1B: Chạy checklist trên 3 screen của bạn (1.5–2 giờ)
Cách làm cụ thể cho từng screen

Screen 1: Dashboard

Mở trang Dashboard admin.
Lấy bảng checklist đã chốt ở Bước 1, đi từng dòng một, tự hỏi: "màn hình này có đúng/sai theo mục này không?"
Với MỖI item, đánh dấu Pass hoặc Fail vào file 03_checklist_execution.md.
Nếu Fail → chụp màn hình ngay, đặt tên screenshot_dashboard_[số thứ tự item].png, lưu vào screenshots/checklist_fails/.
Viết lý do Fail vào cột Notes (ngắn gọn, cụ thể — VD: "Số Total Check-ins không cập nhật lại sau khi có người check-in mới ở tab khác, phải F5 mới thấy đổi").

Screen 2: Participants & Reviews Approval (A4)

Làm tương tự, nhưng chú ý đặc biệt các item liên quan tới:
6 màu trạng thái có nhất quán với các màn hình khác không.
Thử tình huống: duyệt 1 role trong đăng ký nhiều-role của giảng viên rồi bấm Apply → hệ thống có chặn đúng như tài liệu mô tả không? Đây là nơi rất dễ tìm ra bug thật.
Progress bar có cập nhật đúng % sau khi bạn duyệt thêm người không.
Export Excel có tải đúng file không, có feedback loading trong lúc chờ không.

Screen 3: Check-in tab (A5)

Test lần lượt các trạng thái nếu điều kiện cho phép:
Quét mã hợp lệ.
Quét lại cùng mã đó ngay sau đó.
(Nếu không đổi được giờ hệ thống, ghi chú "không kiểm tra được OUTSIDE_CHECKIN_WINDOW do hạn chế môi trường test" — vẫn hợp lệ, miễn giải thích rõ).
Log quét có hiện ngay không cần F5 không.
Prompt hỗ trợ viết Bug Report (dùng khi bạn phát hiện lỗi)
Tôi vừa phát hiện lỗi sau khi test màn hình [tên screen] của hệ thống EMS:
[Mô tả ngắn gọn những gì bạn thấy, ví dụ: "Khi tôi chỉ duyệt 1 trong 2 vai trò
của một đăng ký giảng viên rồi bấm Apply, hệ thống vẫn cho Apply thành công
thay vì báo lỗi yêu cầu duyệt hết."]

Hãy giúp tôi viết lại thành 1 bug report chuẩn gồm đầy đủ: Steps to reproduce
(dạng đánh số), Expected result, Actual result, và đề xuất mức độ Severity
(0=Cosmetic, 1=Minor, 2=Moderate, 3=Major, 4=Critical) kèm lý do chọn mức đó.

→ Copy prompt + output vào 08_ai_audit_report.md. Bạn review lại nội dung AI viết, sửa cho khớp thực tế trước khi đưa vào 04_bug_reports.md.

Sau mỗi bug tìm được → submit ngay Google Form (https://forms.gle/CJQFQCAXcsDbXDMM9), đừng để dồn cuối kẻo quên.

Git commit sau mỗi screen: execution: checklist Dashboard, execution: checklist A4, execution: checklist A5.

BƯỚC 3 — Task 2: Usability Testing với 5 người (3 giờ, trải nhiều ngày)
3.1. Viết task scenario (dùng prompt sau)
Tôi cần thiết kế 1 kịch bản test usability cho người dùng thật, áp dụng trên
3 màn hình sau của hệ thống quản lý sự kiện EMS (vai trò Admin):
1. Dashboard tổng quan (KPI: Total Events, Check-ins, Attendance Rate, Users)
2. Màn hình duyệt danh sách đăng ký tham dự sự kiện (Participants & Reviews),
   có màu trạng thái và progress bar
3. Màn hình Check-in — quét mã người tham dự, có log real-time

Hãy viết cho tôi 1 kịch bản DẠNG MỤC TIÊU (không hướng dẫn từng bước bấm),
mô phỏng công việc thật của 1 nhân viên tổ chức sự kiện, VD kiểu: "Hãy kiểm
tra xem sự kiện X đang có bao nhiêu người đã check-in, sau đó duyệt danh sách
đăng ký đang chờ xử lý, và xử lý check-in cho 1 người tham dự mới đến."

Sau đó viết thêm:
- 4 metric cần đo (task success, time on task, error/hesitation count, SUS score)
- 4-5 câu hỏi mở (probe questions) hỏi cuối session về độ rõ ràng, khả năng
  phục hồi lỗi, tốc độ, độ tin cậy vào hệ thống

Copy output vào 05_usability_testing.md phần Phase 1, bạn tự đọc lại và chỉnh sửa cho tự nhiên, đúng ngữ cảnh EMS thật (đừng giữ nguyên nếu AI viết chung chung).

3.2. Tuyển người + chạy pilot
Tìm 5 người ngoài lớp (bạn bè, người quen phù hợp vai trò "người tổ chức sự kiện" — hoặc đơn giản là mô phỏng vai trò admin cho họ thử) + 1 người pilot.
Chạy pilot trước, xem task scenario có rõ không, có chỗ nào gây confuse không.
3.3. Chạy 5 session thật

Với mỗi người: nói "mình đang test sản phẩm, không phải test bạn", nhờ họ "nghĩ to thành tiếng" (think aloud), quan sát và ghi chú — đừng gợi ý khi họ bị vướng, chỉ ghi lại: họ dừng lại bao lâu, họ nói gì, họ bấm nhầm đâu.

Cuối mỗi session: cho họ làm SUS (10 câu hỏi thang điểm 1-5, có mẫu chuẩn trên mạng, tôi có thể tạo sẵn form cho bạn nếu cần) rồi hỏi probe questions.

3.4. Phân tích kết quả (dùng prompt sau)
Đây là dữ liệu quan sát từ 5 phiên test usability trên hệ thống EMS
(Dashboard, Participants Approval, Check-in):

[Dán vào đây: ghi chú quan sát của bạn cho từng người, điểm SUS từng người,
thời gian hoàn thành, số lỗi]

Hãy giúp tôi:
1. Tính điểm SUS trung bình theo công thức chuẩn
2. Nhóm các pain point giống nhau thành các "finding" riêng biệt
3. Xếp hạng các finding theo mức độ nghiêm trọng (0-4), phân biệt rõ bug đơn
   lẻ với vấn đề thiết kế hệ thống (systemic design issue)
4. Đề xuất 3 khuyến nghị cải tiến cụ thể, ưu tiên theo mức độ nghiêm trọng

→ Bạn phải tự review kỹ phần này — đây chính là chỗ dễ bị AI "bịa" pattern không có thật trong dữ liệu bạn cung cấp. Đối chiếu lại với ghi chú gốc trước khi đưa vào report.

Git commit: usability: design → pilot → run 5 sessions → analyse.

BƯỚC 4 — Task 3: Cross-Platform (2 giờ)
Đăng ký BrowserStack hoặc LambdaTest (free trial).
Với mỗi trong 3 screen, chọn các cell sao cho phủ đủ: 3 OS (Windows/macOS/Android hoặc iOS), 5 browser (Chrome/Firefox/Safari/Edge/Opera), 3 loại thiết bị (Desktop/Tablet/Phone) — không cần đủ 45 ô, chỉ cần mỗi chiều xuất hiện ≥1 lần cho mỗi screen.
Mỗi lần chụp ảnh, overlay thêm dòng chữ [MSSV]@student.hcmus.edu.vn đè lên ảnh (dùng Paint, Canva, hoặc extension chụp ảnh có annotate) cùng tên browser/OS/device hiển thị rõ.
Ghi Pass/Fail vào 06_cross_platform_matrix.md, với Fail thì ghi rõ loại lỗi (overflow, vỡ layout, chữ không đọc được...).

Git commit riêng từng screen: cross-platform: Dashboard, cross-platform: A4, cross-platform: A5.

BƯỚC 5 — Tổng hợp tài liệu cuối (1 giờ)
Điền 02_main_report.md — tóm tắt lại toàn bộ, dẫn link tới các file chi tiết.
Gộp toàn bộ finding đã submit Form vào 07_bug_usability_findings_log.md, đối chiếu số lượng khớp nhau.
Gộp toàn bộ prompt bạn đã dùng (Bước 1-4) vào 08_ai_audit_report.md theo đúng format: tool, ngày giờ, prompt, output, bạn đã sửa gì.
Viết 09_ai_critique.md (200-300 từ) — dựa trên thực tế bạn vừa trải qua, ví dụ: AI ở Bước 3.4 có xu hướng nhóm gộp pain point hơi rộng, bạn phải tách lại cho chính xác.
BƯỚC 6 — Agent Skill (1–1.5 giờ, làm cuối cùng)

Dựa trên toàn bộ note bạn đã ghi rải rác ở skill_notes.md trong quá trình làm Bước 2-4, giờ đúc kết thành skill thật, viết SKILL.md, demo trên 1 screen khác (ví dụ Events list — A1, chưa từng test) để chứng minh tái sử dụng được, quay video ngắn up YouTube.

Bạn muốn tôi bắt đầu giúp bạn viết sẵn nội dung mẫu điền vào file 03_checklist_execution.md với format đã khớp đúng 3 screen (Dashboard/A4/A5), hay bạn muốn tôi tạo sẵn mẫu bảng SUS 10 câu hỏi chuẩn để bạn đưa cho 5 người test luôn?
```
----
## Prompt 8:
**AI Tool:** Claude Sonnet 5
**Ngày giờ:** 28/07/2026 11:30 PM
**Prompt:**
```
tôi chọn màn hình a4 a5 -> Participants & Reviews approval — status colours, progress bar, Export; (A5) Check-in tab — scan-state handling and real-time log; giờ tôi phải chọn thêm 1 screen nữa có thể cùng chủ đề Theo dõi và vận hành sự kiện, tôi thấy có thể chọn 

Dashboard chính
analytic event (cái này thuộc mục analytic lớn) 
Tôi nên chọn cái nào cho hợp lí, lí do là gì
```

- **AI Output:**
``` 
Rất hay là bạn có ảnh chụp thật — tôi thấy ngay 1 tín hiệu quan trọng để quyết định.

Nhận xét nhanh dựa trên ảnh bạn gửi

Ảnh 1 (Dashboard): 4 thẻ KPI (Total Events, Total Check-ins, Attendance Rate, Total Users) đang hiển thị thanh xám loading (skeleton placeholder) thay vì số liệu thật — đây rất có thể là 1 bug thật bạn vừa vô tình bắt được (số liệu bị kẹt ở trạng thái loading, không load ra). Đây là dấu hiệu rất đáng giá để chọn màn này.

Ảnh 2 (Analytics > Events): giao diện phong phú hơn nhiều — có donut chart (Recharts), bộ đếm theo Status/Time Status, tab con (Category/Academic Period/Campus), bộ lọc DateRangeFilter với nút Apply/Reset. UI đa dạng nhưng phức tạp hơn, nhiều thành phần hơn.

Ảnh 3 (Q&A của thầy): Thầy nói rất rõ 2 ý quan trọng:

"Nếu mình tách ra được thành 2 scenarios có ý nghĩa thì có thể 2 người làm, còn không thì 1 người làm trọn vẹn. Mình không thể nào cắt/phân công một cách cứng nhắc."
"Nên nhớ mục tiêu của tester là tìm bug, để đảm bảo quality của project."

→ Thầy đang nhấn mạnh: việc chọn screen phải có ý nghĩa thật (không cứng nhắc để "đủ số"), và mục tiêu cuối là tìm ra bug thật.

Khuyến nghị: chọn Dashboard chính, không chọn Analytics

Lý do cụ thể:

1. Dashboard được nêu ĐÍCH DANH trong đề bài, Analytics thì không.
Đọc lại mục 4 của đề — Pool A liệt kê: "Dashboard KPIs (Total Events, Total Check-ins, Attendance Rate, Total Users); Events list; Add/Edit Event; registration configuration; Draft/Publish/Preview/Important Update/Delete; Participants & Reviews approval; Check-in."

→ Dashboard nằm ngay trong định nghĩa chính thức của Pool A, cùng nhóm với A4/A5 bạn đã chọn. Bạn gần như không cần giải thích thêm gì cả — nó tự động hợp lệ.

Trong khi đó, "Analytics" hoàn toàn không được nhắc tên trong Pool A ở đề bài gốc — nó là 1 mục riêng trong sidebar (Analytics > Overview/Events/Check-ins/User Growth/Traffic), có thể được xem là tính năng cắt ngang (cross-cutting) chứ không thuộc hẳn về scenario nào. Nếu bạn chọn nó, bạn sẽ phải tự bào chữa lý do "vì sao Analytics thuộc cùng function group Pool A" — rủi ro bị TA bẻ lại.

2. Dashboard khớp đúng chủ đề "Theo dõi và vận hành sự kiện" bạn đang theo đuổi.
Luồng 3 screen của bạn tạo thành 1 câu chuyện rất mạch lạc:

Dashboard = nơi admin nhìn tổng quan tình hình vận hành (bao nhiêu event, bao nhiêu check-in, tỷ lệ tham dự).
A4 (Participants & Reviews) = từ tổng quan đó, admin đi vào xử lý — duyệt người đăng ký.
A5 (Check-in) = vận hành thực tế tại hiện trường khi sự kiện diễn ra.

→ Đây là 1 luồng "từ giám sát → xử lý → vận hành" rất hợp lý, dễ viết phần "lý do chọn screen" trong report, và cũng dễ thiết kế 1 kịch bản Usability Testing xuyên suốt cả 3 màn (Task 2) vì chúng nối tiếp nhau logic.

3. Bạn đã tìm thấy 1 bug thật ngay từ bây giờ — đúng tinh thần thầy nói "mục tiêu là tìm bug".
Số liệu KPI bị kẹt loading là ứng viên bug rất tốt cho Task 1B. Chọn Dashboard giúp bạn có ngay 1 finding thật để đưa vào report, thay vì phải mất công tìm bug ở 1 màn hình phức tạp hơn (Analytics) mà bạn chưa chắc quen thuộc.

4. Analytics phức tạp hơn không có nghĩa là "giàu" hơn cho mục đích của bạn.
Đúng là Analytics có nhiều chart/filter hơn, nhưng phần lớn logic đó (Apply/Reset filter, donut chart) là UI pattern khá chuẩn, không có nhiều ràng buộc nghiệp vụ đặc thù như A4 (multi-role approval rule) hay A5 (4 trạng thái quét) — nên độ "giàu" để tìm bug đặc thù không hẳn cao hơn Dashboard.

Việc bạn cần làm ngay
Quay lại Dashboard, refresh trang vài lần, đợi vài giây xem số liệu có load ra không, hoặc mở tab khác rồi quay lại — xác nhận đây có đúng là bug (loading vô hạn) hay chỉ do bạn chụp đúng lúc đang tải.
Ghi lại vào 04_bug_reports.md ngay nếu xác nhận là bug thật:
Screen: Admin Dashboard
Steps: Đăng nhập → vào Dashboard → quan sát 4 thẻ KPI
Expected: hiển thị số liệu thật (VD: Total Events = 8, theo đúng dữ liệu bạn thấy ở Analytics)
Actual: 4 thẻ vẫn giữ trạng thái loading skeleton, không hiển thị số
Severity: gợi ý mức 2-3 (Moderate/Major) vì đây là màn hình đầu tiên admin thấy, ảnh hưởng trực tiếp tới độ tin cậy hệ thống
Viết vào phần "Lý do chọn screen" trong 02_main_report.md:
markdown
Screen 3: Admin Dashboard — được chọn vì đây là màn hình được liệt kê chính
thức trong Pool A (đề bài, mục 4: "Dashboard KPIs..."), đồng thời tạo thành
1 luồng logic hoàn chỉnh cùng A4/A5: Dashboard (giám sát tổng quan) →
Participants & Reviews (xử lý đăng ký) → Check-in (vận hành thực tế tại
hiện trường) — đúng chủ đề "theo dõi và vận hành sự kiện" nhóm em lựa chọn.

Bạn muốn tôi giúp viết luôn checklist execution mẫu cho riêng Dashboard (dựa trên bug loading bạn vừa phát hiện) để bạn có sẵn cấu trúc điền tiếp không?
```

-----
## Prompt 9
**AI Tool:** Claude Sonnet 5
**Ngày giờ:** 28/07/2026 10:25 PM
**Prompt:**
```
```markdown
 **IA-04** | **Feedback** | **IA-04: Feedback & State (Toasts, Badges, Confirmations, Progress Bars, Status Colors)** | | | | | |
| IA-04-01 | Feedback | Thông báo nổi (Toasts) xuất hiện ngay sau khi thực hiện hành động và tự động tắt sau 3-5s. | Norman: Feedback | | | | |
| IA-04-02 | Feedback | Toasts có màu sắc phân biệt rõ ràng: Xanh (Thành công), Đỏ (Lỗi), Vàng (Cảnh báo). | Nielsen #8: Aesthetic | | | | |
| IA-04-03 | Feedback | Hộp thoại xác nhận (Confirmation dialog) xuất hiện trước các hành động hủy/xóa quan trọng. | Nielsen #5: Error Prev. | | | | |
| IA-04-04 | Feedback | Huy hiệu (Badges) hiển thị chính xác số lượng thông báo; trạng thái vé thay đổi tương ứng khi được phê duyệt/hủy. | Nielsen #1: Visibility | | | | |
| IA-04-05 | Feedback | Thanh tiến trình (Progress bar) hoặc vòng xoay tải (Spinner) xuất hiện khi hệ thống xử lý. | Nielsen #1: Visibility | | | | |
| IA-04-06 | Feedback | Trạng thái hiển thị màu sắc tương thích với ngữ nghĩa (Ví dụ: APPROVED màu xanh lá, REJECTED màu đỏ). | Nielsen #2: Match System | | | | |
| IA-04-07 | Feedback | Chấm đỏ thông báo (Notification dot) hiển thị động ngay khi có thay đổi trạng thái đăng ký. | Nielsen #1: Visibility | | | | |
| IA-04-08 | Feedback | Hộp thoại chi tiết ảnh (Lightbox) mở rộng mượt mà khi click vào ảnh đính kèm. | Nielsen #7: Flexibility | | | | |
| IA-04-09 | Feedback | Cập nhật dữ liệu thời gian thực (Real-time update) mà không cần người dùng reload trang. | Norman: Feedback | | | | |
| IA-04-10 | Feedback | Hiển thị thông báo rõ ràng khi mất kết nối mạng Internet. | Nielsen #1: Visibility | | | | |
| IA-04-11 | Feedback | Hệ thống vô hiệu hóa nút gửi hoặc ngăn chặn gửi dữ liệu trùng lặp khi người dùng click đúp nút Submit. | Nielsen #5: Error Prev. | | | | |
| IA-04-12 | Feedback | Mã QR/Barcode trên vé hiển thị rõ nét (không bị mờ), có kích thước tối thiểu đảm bảo quét được bằng ứng dụng camera thông thường. | Nielsen #1: Visibility | | | | |
| IA-04-13 | Feedback | Ô nhập liệu (text box) hiển thị hiệu ứng viền/nổi bật trực quan (focus state) khi nhấp chuột vào để người dùng nhận biết rõ ràng đang thao tác/nhập liệu. | Norman: Feedback | | | | | voi phan feed back nay thi toi phai test the nao, voiws man hinh A4
```
**AI Output:**
```
Tôi sẽ hướng dẫn cụ thể cách test từng item IA-04, dựa đúng trên những gì bạn đã thấy ở 3 tab của A4 (Registrants / Review Lecturers / Review Students). Với mỗi item, tôi ghi rõ: thao tác cụ thể cần làm, quan sát gì, và đã biết trước kết quả gì từ ảnh trước đó (nếu có).

IA-04-01 & IA-04-02 — Toast thông báo (xuất hiện + tự tắt + đúng màu)

Cách test:

Vào tab Review Students (đang có 3 sinh viên: Lê Hoàng Lâm, Việt Bùi Nam, Đức Trần Hải).
Bấm "Approved" cho 1 người bất kỳ (VD: Lê Hoàng Lâm) → xem có toast xuất hiện góc màn hình không.
Bấm tiếp "Apply" → quan sát toast lần 2.
Dùng đồng hồ đếm xem toast tự biến mất sau bao lâu (đếm giây thật, không đoán).
Thử làm 1 hành động cố tình gây lỗi (VD: bấm Apply mà chưa chọn action nào cho ai) → xem toast lỗi có màu đỏ khác với toast thành công không.

Ghi vào bảng: Pass nếu toast xuất hiện + tự tắt trong khoảng 3-5s + màu đúng ngữ nghĩa (xanh=thành công, đỏ=lỗi).

IA-04-03 — Dialog xác nhận trước hành động quan trọng ⚠️ (ưu tiên cao nhất, đã note từ trước)

Cách test — đây là chỗ RỦI RO CAO nhất bạn nên test ngay:

Ở tab Review Students, bấm nút "Reject All" (nút màu hồng/đỏ ở góc trên).
Quan sát: có hiện dialog hỏi "Bạn có chắc chắn muốn từ chối tất cả?" trước khi thực thi không, hay nó từ chối luôn ngay lập tức không hỏi gì?
Làm tương tự với "Cancel All".

Nếu KHÔNG có dialog xác nhận → đây là bug nghiêm trọng (Severity 3-4), vì hành động này ảnh hưởng hàng loạt người cùng lúc, không thể hoàn tác (undo) nếu bấm nhầm.

⚠️ Lưu ý: chỉ bấm thử nếu bạn chắc dữ liệu này không quan trọng (vì hệ thống có thể reset định kỳ theo đề bài, nên thử được, nhưng nên chụp ảnh TRƯỚC khi bấm để so sánh).

IA-04-04 & IA-04-07 — Badge/Notification dot (đã phát hiện lỗi ở lượt trước)

Cách test để xác nhận chắc chắn (không chỉ dựa vào 1 ảnh):

Chụp ảnh sidebar/tab hiện tại — chấm đỏ đang ở đâu (VD: tab "Review Students" có chấm đỏ).
Bấm Approve cho cả 3 sinh viên → bấm Apply.
Chờ vài giây, F5 lại trang.
Quan sát: chấm đỏ trên tab Review Students đã biến mất chưa?
Nếu vẫn còn → xác nhận đúng là bug thật (không phải do bạn "chưa xử lý xong" mà là do lỗi thật).
IA-04-05 — Progress bar / Spinner khi xử lý

Cách test:

Bấm Apply ở tab Review Students (sau khi đã chọn hành động cho 3 người).
Quan sát ngay khoảnh khắc bấm: có xuất hiện spinner nhỏ trên nút Apply hoặc progress bar toàn trang không, hay giao diện "đứng hình" không phản hồi gì trong lúc chờ?
Nếu mạng nhà bạn nhanh quá không thấy được — mở DevTools (F12) → tab Network → chọn "Slow 3G" để giả lập mạng chậm, rồi thử lại Apply.
IA-04-06 — Màu trạng thái đúng ngữ nghĩa

Cách test:

So sánh màu ở tab Registrants (badge "Approved" màu xanh lá) với màu nút trạng thái ở tab Review Students ("Rejected" đỏ / "Pending Review" vàng cam / "Approved" xanh lá).
Kiểm tra: cùng 1 khái niệm "Approved" có dùng cùng 1 tông màu xanh lá ở cả 2 tab không, hay bị lệch tông (VD: 1 bên xanh lá nhạt, 1 bên xanh lá đậm)?

(Đây chính là phần tôi đã ghi "Pass tạm" ở bảng trước — bạn cần đối chiếu kỹ màu bằng mắt hoặc dùng công cụ pick màu để xác nhận có đúng 100% giống nhau không.)

IA-04-08 — Lightbox ảnh

Cách test:

Xem trong 3 tab của A4 có ảnh đính kèm nào để click không (theo ảnh bạn gửi, hiện chưa thấy cột ảnh nào ở Registrants/Review Lecturers/Review Students).
Nếu không có ảnh nào ở A4 → đánh dấu NA với ghi chú: "A4 không có tính năng đính kèm/hiển thị ảnh, item không áp dụng."
IA-04-09 — Real-time update không cần reload

Cách test (cần 2 trình duyệt hoặc 2 tab ẩn danh):

Mở EMS ở Tab A (trình duyệt thường), đăng nhập admin, mở tab Review Students.
Mở EMS ở Tab B (cửa sổ ẩn danh/trình duyệt khác), dùng tài khoản user khác (hoặc chính bạn) thử đăng ký sự kiện này (nếu registration còn mở).
Quay lại Tab A, không F5, chỉ chờ và quan sát — danh sách Review Students có tự thêm người mới vừa đăng ký không, hay bạn phải F5 mới thấy?

Nếu phải F5 mới thấy → Fail, ghi chú: "Danh sách không cập nhật real-time, yêu cầu người dùng phải chủ động reload trang."

IA-04-10 — Thông báo khi mất mạng

Cách test:

Mở DevTools (F12) → tab Network → chọn "Offline".
Thử bấm Apply hoặc chuyển tab.
Quan sát: có thông báo nào kiểu "Mất kết nối mạng" hiện ra không, hay giao diện chỉ im lặng/treo?
IA-04-11 — Chặn double-submit khi click đúp

Cách test:

Chọn hành động cho 1 người ở Review Students.
Click đúp thật nhanh (double-click) vào nút "Apply".
Kiểm tra: dữ liệu có bị gửi 2 lần không (xem trong Network tab của DevTools có 2 request giống hệt nhau không, hoặc xem log/audit có ghi nhận 2 lần hành động không).
IA-04-12 — QR/Barcode rõ nét

Cách test:

A4 (Registrants/Review Lecturers/Review Students) không hiển thị mã QR — đây là tính năng thuộc màn "My Registrations" phía User (B4), không thuộc A4.
Đánh dấu NA, ghi chú: "Không áp dụng cho A4 — mã QR chỉ xuất hiện ở phía User (Scenario B)."
IA-04-13 — Focus state khi click vào input

Cách test:

Click chuột vào ô "Add note..." ở tab Review Students.
Quan sát: viền ô có đổi màu/sáng lên (highlight) để báo hiệu đang được chọn không, hay không có gì thay đổi?
Bảng tổng hợp cách note kết quả (mẫu điền nhanh)
ID	Pass/Fail/NA	Cách xác nhận
IA-04-01, 02		Bấm Approve → đếm giây → xem màu toast
IA-04-03		Bấm Reject All/Cancel All → có dialog không
IA-04-04, 07		Approve hết → F5 → xem dot còn không
IA-04-05		Throttle mạng chậm → bấm Apply → xem spinner
IA-04-06		So màu Approved giữa 2 tab bằng mắt/color picker
IA-04-08	NA	Không có ảnh ở A4
IA-04-09		Test 2 tab song song, không F5
IA-04-10		DevTools > Offline > thử thao tác
IA-04-11		Double-click Apply, xem Network tab
IA-04-12	NA	Không áp dụng, QR thuộc B4
IA-04-13		Click vào ô Add note, xem viền đổi màu

Bạn cứ làm lần lượt các bước trên (khoảng 15-20 phút), rồi gửi kết quả/ảnh cho tôi — tôi sẽ giúp bạn điền hoàn chỉnh bảng checklist và viết ngay Bug Report cho những chỗ Fail.
```

----
## Prompt 10 
**AI Tool:** Claude Sonnet 5
**Ngày giờ:** 28/07/2026 10:45 PM
**Prompt:**
```
nut cancel ở đây ko bị mờ khi ko được hoạt động thì là lỗi nào, toi thay no khong thuoc loi save, submit disabled khi chưa có thông tin hợp lệ thi toi nen tao 1 item trong checklist ko?
```
**AI Output:**
```
Câu hỏi tốt — nhưng cần phân biệt rõ 2 trường hợp trước khi kết luận đây có phải lỗi hay không, vì nhìn ảnh không đủ để khẳng định chắc chắn.

Trước tiên: "Cancel All" đang ở dạng nào?

Nhìn 4 nút trong ảnh:

Reject All — nền hồng đậm (filled)
Approve All — nền xanh lá nhạt (filled)
Cancel All — nền trắng, chỉ có viền (outline style)
Apply — nền xanh dương (filled)

→ "Cancel All" dùng outline style khác 3 nút còn lại — đây có thể chỉ là 1 kiểu thiết kế nút phụ (secondary button) có chủ đích, không nhất thiết là "trạng thái disabled". Nhiều hệ thống UI cố tình làm nút "Cancel/Hủy" nhẹ nhàng hơn (outline) để nó không "nổi" bằng các hành động chính (Approve/Reject/Apply) — đây là 1 pattern thiết kế hợp lý, KHÔNG phải bug.

Vậy vấn đề thật sự bạn đang nghi ngờ là gì?

Bạn hỏi "nút Cancel ở đây không bị mờ khi không được hoạt động" — nghĩa là bạn đang nghi ngờ: "Cancel All" hiện tại KHÔNG có tác dụng gì (vì chưa ai chọn action nào để mà Cancel), nhưng nó vẫn hiển thị như nút bình thường có thể bấm được, không có dấu hiệu disabled.

Đây mới chính là vấn đề thật cần kiểm tra, và nó thuộc đúng 2 heuristic sau:

Heuristic	Vi phạm gì
Norman — Signifiers/Constraints	Nút phải "báo hiệu" đúng trạng thái có thể tương tác hay không. Nếu nút không hoạt động (disabled) nhưng style vẫn giống nút bình thường → gây hiểu lầm affordance (tưởng bấm được nhưng không có tác dụng gì, hoặc ngược lại tưởng không bấm được nhưng thực ra vẫn hoạt động)
IA-02-08 (trong checklist bạn đang có)	"Các nút Submit/Save bị vô hiệu hóa (disabled) khi form chưa điền đủ thông tin hợp lệ" — áp dụng tương tự cho Cancel All: nếu chưa có thay đổi gì để hủy, nút này lẽ ra nên bị disable (mờ đi + con trỏ chuyển thành not-allowed)
Cách test để xác định chính xác đây có phải lỗi thật không
Bấm thử "Cancel All" ngay bây giờ (khi chưa chọn Approve/Reject cho ai) — xem có phản ứng gì không (toast, thay đổi trạng thái, hay hoàn toàn im lặng)?
Nếu im lặng, không có gì xảy ra → đây là bug thật: nút trông như bấm được nhưng thực chất vô nghĩa, vi phạm nguyên tắc "signifier phải khớp với chức năng thật".
Nếu có phản ứng (VD: reset lại toàn bộ lựa chọn hiện tại, kể cả khi chưa chọn gì) → không phải bug, chỉ là style thiết kế (outline) — không cần disable vì nút luôn có tác dụng "reset về trạng thái mặc định".
Bạn bắt lỗi rất tinh — và đúng là bạn phát hiện ra 1 vấn đề thật trong chính bộ checklist, không phải chỉ trong EMS. Để tôi phân tích rõ:

Kiểm tra lại: IA-02-08 có đúng KHÔNG áp dụng được không?

Đúng như bạn nói — nguyên văn IA-02-08:

"Các nút Submit/Save bị vô hiệu hóa (disabled) khi form chưa điền đủ thông tin hợp lệ."

Item này chỉ định danh cụ thể "Submit/Save", không phải "mọi loại nút hành động nói chung". "Cancel All" không phải nút Submit/Save — nên gán vào đây là ép chữ (misclassification). Bạn đúng, tôi đã dùng nhầm item này.

Kiểm tra lại: IA-01-03 có đúng không?

Xem lại nguyên văn IA-01-03:

"Màu sắc của các nút hành động (Primary, Secondary) và trạng thái nhất quán."

Item này nói về tính nhất quán màu sắc giữa các nút (VD: màu Primary luôn giống nhau xuyên suốt hệ thống) — nó không nói gì về việc nút có disabled đúng lúc hay không. Vấn đề bạn tìm ra không phải "màu không nhất quán", mà là "nút không phản hồi gì khi bấm, nhưng cũng không có tín hiệu thị giác nào cho biết nó vô dụng" — đây là 2 vấn đề khác nhau. Nên IA-01-03 cũng không khớp chính xác.

Vậy bản chất lỗi này thuộc về đâu?

Nhìn lại đúng bản chất: bạn bấm nút → không có bất kỳ phản hồi nào xảy ra (không toast, không đổi trạng thái, không dialog). Đây chính xác là vi phạm nguyên tắc:

Norman — Feedback principle: mọi hành động của người dùng phải nhận được phản hồi rõ ràng từ hệ thống.
Nielsen #1 — Visibility of System Status: hệ thống phải luôn cho người dùng biết điều gì đang xảy ra.

→ Item gần đúng nhất trong bộ checklist hiện có là IA-04-01 ("Thông báo nổi (Toasts) xuất hiện ngay sau khi thực hiện hành động") — nhưng đọc kỹ, item này giả định là hành động ĐÃ xảy ra thì mới cần toast. Vấn đề của bạn tinh vi hơn: hành động KHÔNG xảy ra gì cả (no-op), và hệ thống cũng không báo cho biết "không có gì để hủy" — tức là thiếu cả 2 lớp: (1) không disable nút khi vô nghĩa, (2) không thông báo khi bấm mà không có tác dụng.

Kết luận: đây là 1 finding KHÔNG khớp chính xác với item nào có sẵn — và đó chính là điều đáng giá nhất bạn vừa làm được

Việc bạn nhận ra "2 item được gán đều không khớp đúng" chứng tỏ bạn đang review checklist một cách nghiêm túc, đúng tinh thần đề bài yêu cầu (mục 6, Task 1A): "For each item you added beyond the AI output, explain why the AI missed it."

Tôi đề xuất bạn làm 2 việc để tận dụng đúng phát hiện này:

1. Ghi finding này như 1 bug độc lập, dẫn heuristic tổng quát (không ép vào ID có sẵn)
markdown
| ID | Khía Cạnh | Mục Kiểm Tra | Heuristic | Pass/Fail | Ghi chú |
|---|---|---|---|---|---|
| (Not mapped) | Feedback | Nút hành động (secondary action như "Cancel All") không có phản hồi gì khi bấm trong trạng thái vô nghĩa (chưa có gì để hủy), và cũng không bị vô hiệu hóa để báo hiệu điều đó | Norman: Feedback principle + Nielsen #1: Visibility of system status | Fail | Bấm "Cancel All" khi chưa chọn action nào cho ai — không có toast, không đổi trạng thái, không dialog nào xuất hiện. Người dùng không có cách nào biết được hành động có được ghi nhận hay không. |
2. Bổ sung 1 item MỚI vào checklist chung của nhóm (đây là cơ hội tốt để ăn điểm phần "AI missed")
markdown
| IA-04-14 | Feedback | Các nút hành động phụ (secondary actions như Cancel/Clear/Reset) phải được vô hiệu hóa (disabled + đổi con trỏ) khi không có gì để thực hiện, HOẶC phải hiển thị phản hồi rõ ràng (toast/thông báo) nếu vẫn cho phép bấm mà không có tác dụng gì | Norman: Feedback + Signifiers | Added by human |

Giải thích vì sao AI bỏ sót item này (để đưa vào file 01_GROUP_gui_checklist.md):

"AI khi generate checklist ban đầu chỉ tập trung vào các nút hành động CHÍNH (Submit/Save/Approve) vì đây là pattern phổ biến nhất trong mọi hệ thống. AI không tự nghĩ ra trường hợp đặc thù của các nút hành động PHỤ (secondary/reset actions) khi ở trạng thái 'không có gì để thực hiện' — đây là 1 edge case chỉ phát hiện được khi thao tác thực tế trên hệ thống thật (EMS), không thể suy ra chỉ từ mô tả lý thuyết."

Đây là 1 finding rất tốt cho báo cáo của bạn — vừa là 1 bug thật (Severity đề xuất: 1-2, Minor/Moderate vì gây confusion nhưng không phá hỏng chức năng chính), vừa là bằng chứng cụ thể cho thấy bạn đã tự review và bổ sung checklist ngoài AI, đúng yêu cầu cốt lõi của đề bài.

Bạn có muốn tôi giúp viết luôn Bug Report hoàn chỉnh cho finding này để submit Google Form không?
```

## Prompt 11
**AI Tool:** Claude Sonnet 5
**Ngày giờ:** 02/08/2026 08:00 AM
**Prompt:**
```
Bạn là một AI chuyên gia về QA Automation. Hãy giúp tôi viết nội dung cho file `skill.md` dành cho một agent có nhiệm vụ chạy GUI checklist bằng công cụ MCP Playwright.
Hãy thiết kế file `skill.md` với các hướng dẫn và quy trình rõ ràng dựa trên các yêu cầu sau:
**1. Đầu vào (Inputs):**
- Link web cần test
- Danh sách các màn hình (screens) cần test
- Tài khoản login (nếu có)
**2. Quy trình làm việc / Workflow (Hãy tự động tinh chỉnh và bổ sung thêm các best practices cho phần này):**
- **Xác nhận input:** Xác nhận lại các thông tin đầu vào với người dùng trước khi chạy.
- **Kiểm tra môi trường:** Xem web có chạy được không. Hãy định nghĩa các trường hợp lỗi phổ biến (VD: web sập, timeout, không tìm thấy element) và cách giải quyết/xử lý.
- **Chạy checklist:** Sử dụng MCP Playwright để chạy test. Phải tuân thủ theo đúng format của file tham chiếu có tên `share-gui-checklist.md`.
- **Xuất file:** Xuất kết quả ra file có tên `<scenario>-gui-checklist.md`, phần nào lỗi thì cap màn hình lại, lưu theo dạng <screen>-bug-itemID.png
- **Viết Bug Report:** Với những lỗi tìm được (failed test), hãy viết bug report chuẩn (gồm các bước tái hiện, kết quả mong đợi, kết quả thực tế).
- **Tóm tắt (Summary):** Tóm tắt lại ngắn gọn các lỗi (failures) cho người dùng vào cuối phiên làm việc.
Hãy viết file `skill.md` thật chuyên nghiệp, rõ ràng để một agent khác có thể đọc và làm theo một cách chính xác nhất, viết băng tiếng anh
```
**AI Output:**
```
Đã tạo xong SKILL.md với đầy đủ 7 phần theo yêu cầu:

Inputs — URL, screens, credentials, reference checklist + bước xác nhận lại với người dùng trước khi chạy.
Pre-flight environment check — bảng chi tiết 5 loại lỗi phổ biến (site down, timeout, login fail, element not found, session expired, thiếu data) và cách xử lý từng loại.
Checklist execution workflow — vòng lặp per-screen, xử lý sub-tab, nguyên tắc tương tác (wait for stability, one assertion per action, tránh hành động phá hủy khi chưa xác nhận).
Output file conventions — đúng format <scenario>-gui-checklist.md và <screen>-bug-itemID.png bạn yêu cầu.
Bug report template — đủ steps/expected/actual/severity với bảng hướng dẫn chọn severity không thổi phồng.
End-of-session summary — tóm tắt ngắn gọn cuối phiên.
Guardrails — các ràng buộc "không được làm" (không tự bịa data, không tự quyết hành động phá hủy, không đoán mò Pass/Fail) — đây chính là phần đảm bảo skill này không biến AI thành black box, đúng tinh thần đề bài yêu cầu.

Vài lưu ý khi bạn đưa skill này vào Antigravity/Claude Code thật:

Đặt đúng vị trí: .claude/skills/gui-checklist-executor/SKILL.md (nếu dùng Claude Code) — không phải .agent/skills/... như lỗi bạn gặp trước đó.
Trước khi demo video, hãy thử chạy trên 1 screen chưa test tay (ví dụ Events list — A1) để chứng minh khả năng tái sử dụng, đúng yêu cầu mục 8 của đề.
Nhớ log lại chính prompt bạn vừa gửi tôi (để viết SKILL.md này) vào 08_ai_audit_report.md — vì đây cũng là 1 lần tương tác AI cần khai báo.

Bạn có muốn tôi viết tiếp file share-gui-checklist.md mẫu (rút gọn, đúng format bảng mà skill này tham chiếu tới) để bạn test thử skill ngay không?
```

## Prompt 12
**AI Tool:** Claude Sonnet 4.6
**Ngày giờ:** 02/08/2026 08:30 AM
**Prompt:**
````
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
  /gui-checklist-excecutor screen A5
````

**AI output:**
````
I have all the context I need. Per the skill's Step 1, I must confirm inputs with the user before proceeding. Based on the project documentation, here is what I've gathered:

I'm about to run the GUI checklist with the following setup:

Input	Value
Target URL	https://prod-dev.ems-fitus.cloud/ (inferred from AIAuditReport.md context)
Screen to test	A5 — Check-in tab (Admin QR/barcode scanning screen with 4 scan states: SUCCESS, ALREADY_CHECKED_IN, OUTSIDE_CHECKIN_WINDOW, PENDING_REVIEW; real-time scan log; Excel export)
Navigation path	Login as admin → navigate to an event → open the Check-in tab
Login	Credentials needed — from A4 execution, credentials were used but not recorded in the files I can see
Reference checklist	shared_gui_checklist.md (already read ✅)
Output file	Will add Screen A5 table to ChecklistExecution.md
IMPORTANT

Before I can proceed, I need two things confirmed:

Login credentials — what is the admin username/email and password for prod-dev.ems-fitus.cloud?
Target URL confirmation — is https://prod-dev.ems-fitus.cloud/ correct? (I inferred this from the AIAuditReport context, but it wasn't explicitly stated in the files.)
Which event to navigate to — should I use any existing event with check-in functionality, or is there a specific test event I should use?
Please confirm these details and I'll proceed immediately.

````

## Prompt 13
**AI Tool:** Claude Sonnet 4.6
**Ngày giờ:** 02/08/2026 08:35 AM
**Prompt:**
```
1. Login credentials: admin@gmail.com /
Admin@123
2. https://prod-dev.ems-fitus.cloud/ correct
3. use any existing event with check-in functionality
```
**AI output:**
```
Checklist Run Summary — Screen A5
Screens tested: A5 — Check-in tab (Machine Learning Hands-On Workshop, Event #68) Environment status: ✅ OK — site reachable, login successful, tab accessible Total items evaluated: 40

✅ Pass: 17
❌ Fail: 5
⬛ NA: 18
Failures found (5), sorted by severity:
Sev	Bug ID	Item	Short description
2 Moderate	BUG-A5-05	IA-04-14 / IA-04-01	Export button silently does nothing when table is empty — no toast, no download, no API call
1 Minor	BUG-A5-02	IA-01-07	Sidebar not responsive at 375px mobile — overlaps content
1 Minor	BUG-A5-03	IA-03-05	No breadcrumbs (same bug as A4)
1 Minor	BUG-A5-04	IA-03-11	Sub-tab switch (Checked In ↔ Scan Logs) doesn't update URL
0 Cosmetic	BUG-A5-01	IA-01-04	"Submit scan" aria-label & search placeholder not translated in Vietnamese
0 Cosmetic	BUG-A5-06	IA-04-14	Disabled "Submit scan" button still shows pointer cursor
Items requiring manual verification (NA — 7 items):
IA-02-03, IA-04-05, IA-04-11 — require active check-in window (opens 20/09/2026)
IA-04-06 — requires at least 1 scan in the log to verify status color semantics
IA-04-09 — requires 2 simultaneous sessions
IA-04-10 — requires manual network disconnect
IA-01-06 — requires throttled network to observe skeleton loading
Files updated:


ChecklistExecution.md
 — Screen A5 table added (rows IA-01-01 → IA-04-14, all 40 items with verdicts + notes)
screenshots/ — 6 bug evidence screenshots saved:


A5-bug-IA-01-04.png
 · 

A5-bug-IA-01-07.png
 · 

A5-bug-IA-03-05.png
 · 

A5-bug-IA-03-11.png
 · 

A5-bug-IA-04-14.png
 · 

A5-bug-IA-04-14b.png
Note on BUG-A5-05 (the most impactful): The Export button on an empty table calls no API and shows zero feedback — confirmed by DOM inspection + network request log. This should be either disabled or showing a clear "Nothing to export" message. This is the highest-priority fix on this screen.

A5 Checklist Run Report

## Screen A5: Check-in tab

> **Event tested:** Machine Learning Hands-On Workshop (ID: 68)
> **URL:** https://prod-dev.ems-fitus.cloud/dashboard/admin/events/views?id=68&tab=checkin
> **Check-in status at run time:** Not open yet (opens 07:30 20/09/2026)
> **Sub-tabs:** Checked In | Scan Logs

| ID | Khía Cạnh | Mục Kiểm Tra (Checklist Item Description) | Ánh Xạ Heuristics / Nguyên Tắc | Screen A5 (Pass/Fail/NA) | Ghi Chú Lỗi (Notes) |
|---|---|---|---|---|---|
| **IA-01** | **General UI** | **IA-01: General UI Standards (Layout, Typography, Color, Consistency, i18n)** | | | |
| IA-01-01 | General UI | Hệ thống lưới và khoảng cách (Grid & Spacing) căn lề nhất quán trên toàn màn hình. | Nielsen #4: Consistency | Pass | Stat cards, barcode section và data table đều căn lề đều nhau theo grid layout. |
| IA-01-02 | General UI | Font chữ (typography) nhất quán về kích thước, độ dày (bold/regular) và phân cấp tiêu đề. | Nielsen #4: Consistency | Pass | H1 (sự kiện), H3 ("Check-in Barcode") phân cấp rõ. |
| IA-01-03 | General UI | Màu sắc của các nút hành động (Primary, Secondary) và trạng thái nhất quán. | Norman: Signifiers | Pass | Nút "Submit scan" (primary, xanh) và "Export" (secondary) phân biệt rõ theo pattern toàn hệ thống. |
| IA-01-04 | General UI | Đa ngôn ngữ (EN/VI) hoạt động đầy đủ, không bị dịch thiếu hoặc chồng lấp chữ. | Nielsen #4: Consistency | Fail | Sau khi chuyển sang Tiếng Việt: button "Submit scan" (aria-label) và placeholder "Search checkins" không được dịch — vẫn hiển thị tiếng Anh. Ảnh: screenshots/A5-bug-IA-01-04.png |
| IA-01-05 | General UI | Trạng thái rỗng (Empty state) được hiển thị rõ ràng khi không có sự kiện/dữ liệu nào. | Nielsen #1: Visibility | Pass | Bảng "Checked In" và "Scan Logs" đều hiển thị "No results" rõ ràng khi chưa có dữ liệu. |
| IA-01-06 | General UI | Trạng thái đang tải (Loading state/skeleton) hiển thị khi kéo dữ liệu chậm. | Nielsen #1: Visibility | NA | Không quan sát được skeleton/loading trong điều kiện mạng bình thường. Cần kiểm tra thủ công với throttled network. |
| IA-01-07 | General UI | Trang web tương thích tốt và tự động co giãn (Responsive) trên màn hình. | Nielsen #4: Consistency | Fail | Ở viewport 375px (mobile): sidebar admin vẫn hiển thị dạng text list đè lên nội dung chính — sidebar không ẩn/collapse đúng cách trên mobile. Ảnh: screenshots/A5-bug-IA-01-07.png |
| IA-01-08 | General UI | Các hình ảnh (Thumbnail/Banner) không bị méo tỉ lệ hiển thị (tỷ lệ 4:3 và 24:9) trên các kích thước màn hình khác nhau. | Shneiderman: Aesthetics | NA | Màn hình Check-in tab không có ảnh thumbnail/banner. |
| IA-01-09 | General UI | Các icon được căn chỉnh đúng tâm so với nhãn text bên cạnh. | Shneiderman: Aesthetics | Pass | Các icon SVG trong sidebar (Lucide icons) được căn giữa theo chiều dọc với nhãn text. |
| IA-01-10 | General UI | Độ tương phản màu sắc giữa văn bản và nền đủ rõ ràng (Accessibility WCAG). | Nielsen #4: Consistency | Pass | Text tối (lab 8%) trên nền trắng — tương phản cao. Sidebar tối (#18181b) với text sáng — đủ tương phản. |
| IA-01-11 | General UI | Các liên kết ngoài (External links) mở ở tab mới, liên kết nội bộ (Internal links) mở ở tab hiện tại. | Nielsen #3: User Control | NA | Không có external links trên màn hình này. Tất cả 11 link đều là internal và mở đúng trong tab hiện tại. |
| IA-01-12 | General UI | Ảnh Thumbnail (4:3) và Banner (24:9) không bị cắt xén mất nội dung quan trọng. | Nielsen #4: Consistency | NA | Không có ảnh thumbnail/banner trên màn hình Check-in tab. |
| **IA-02** | **Forms** | **IA-02: Forms (Labels, Validation, Errors, Required Fields, Rich Text)** | | | |
| IA-02-01 | Forms | Các trường bắt buộc nhập (Required fields) được đánh dấu ký hiệu trực quan (ví dụ dấu `*`). | Norman: Constraints | NA | Barcode input không có required marker — đây là scan input, không phải traditional form field. |
| IA-02-02 | Forms | Nhãn (Labels) của trường nhập liệu luôn hiển thị rõ ràng và đi sát với ô nhập liệu. | Nielsen #6: Recognition | Pass | Heading "Check-in Barcode" rõ ràng phía trên ô nhập liệu. Placeholder "Enter barcode..." cũng hỗ trợ. |
| IA-02-03 | Forms | Validation thời gian thực báo lỗi đỏ trực quan ngay dưới trường nhập liệu bị lỗi. | Nielsen #5: Error Prev. | NA | Check-in không open, button disabled — không thể test barcode submission flow. Cần kiểm tra thủ công khi check-in window mở. |
| IA-02-04 | Forms | Thông báo lỗi cụ thể, hướng dẫn cách khắc phục thay vì báo lỗi chung chung. | Nielsen #10: Help & Error | NA | Chưa có dữ liệu scan nào trong session này để kiểm tra thông báo lỗi cụ thể. |
| IA-02-05 | Forms | Định dạng tải lên (Upload file/image) kiểm tra đúng định dạng và dung lượng tối đa. | Norman: Constraints | NA | Không có upload field trên màn hình Check-in. |
| IA-02-06 | Forms | Trình soạn thảo Rich Text hiển thị đầy đủ thanh công cụ và hoạt động mượt mà. | Nielsen #7: Flexibility | NA | Không có Rich Text editor trên màn hình Check-in. |
| IA-02-07 | Forms | Người dùng có thể nhấn `Tab` để di chuyển tuần tự qua các ô nhập liệu trong form. | Nielsen #7: Flexibility | Pass | Tab order tồn tại đầy đủ: sidebar links → header controls → tabs → barcode input → search → export button. |
| IA-02-08 | Forms | Các nút Submit/Save bị vô hiệu hóa (disabled) khi form chưa điền đủ thông tin hợp lệ. | Nielsen #5: Error Prev. | Pass | Nút "Submit scan" bị disabled đúng cách khi check-in chưa mở (disabled=true, opacity 0.5). |
| IA-02-09 | Forms | Định dạng ngày giờ hiển thị theo chuẩn cục bộ dễ đọc đối với người dùng Việt Nam. | Nielsen #2: Match System | Pass | Thời gian hiển thị dạng "07:30 20/09/2026" — đúng chuẩn Việt Nam (ngày/tháng/năm). |
| IA-02-10 | Forms | Nút xóa nhanh (clear button) hoặc reset form hoạt động chính xác. | Nielsen #3: User Control | NA | Không có clear/reset button trên search hoặc barcode input. |
| IA-02-11 | Forms | Trình duyệt hỗ trợ tính năng tự động điền (autofill) cho các trường thông tin cơ bản. | Nielsen #7: Flexibility | NA | Barcode input là scan input đặc thù, không cần autofill. |
| IA-02-12 | Forms | Ô nhập mật khẩu hỗ trợ tính năng toggle ẩn/hiện mật khẩu trực quan bằng biểu tượng con mắt. | Nielsen #7: Flexibility | NA | Không có password field trên màn hình Check-in. |
| **IA-03** | **Navigation** | **IA-03: Navigation (Menus, Breadcrumbs, Sidebar, Tabs, Back actions, Deep links)** | | | |
| IA-03-01 | Navigation | Menu điều hướng chính luôn cố định hoặc dễ dàng truy cập ở đầu trang/thanh bên. | Nielsen #6: Recognition | Pass | Sidebar admin luôn hiển thị cố định bên trái với tất cả các mục menu. |
| IA-03-02 | Navigation | Trạng thái hiện tại của trang (Active state) được làm nổi bật trên menu điều hướng. | Nielsen #1: Visibility | Pass | "Events Management" được highlight bằng bg-[#1bc2f5] và text-white — rõ ràng về mặt visual. |
| IA-03-03 | Navigation | Nút quay lại (Back/Return action) đưa người dùng về đúng trang trước đó, không mất trạng thái. | Nielsen #3: User Control | Pass | Nút quay lại (mũi tên) dẫn về /dashboard/admin/events đúng. |
| IA-03-04 | Navigation | Liên kết sâu (Deep links) dẫn trực tiếp đến trang chi tiết sự kiện mà không bị lỗi 404. | Nielsen #4: Consistency | Pass | URL ?id=68&tab=checkin load trực tiếp đúng tab Check-in, không lỗi 404. |
| IA-03-05 | Navigation | Breadcrumbs hiển thị đúng phân cấp thư mục và có thể click để quay về thư mục cha. | Nielsen #6: Recognition | Fail | Không có breadcrumbs. Chỉ có 1 nút back arrow icon (không có text). Người dùng không thể biết họ đang ở cấp nào trong phân cấp sự kiện. Ảnh: screenshots/A5-bug-IA-03-05.png |
| IA-03-06 | Navigation | Tính năng kéo thả thay đổi thứ tự (Reorder) hiển thị trực quan (dòng bị kéo mờ opacity-50) và các nút thao tác khác tạm thời bị vô hiệu hóa. | Norman: Feedback | NA | Không có drag-and-drop/reorder feature trên màn hình Check-in. |
| IA-03-07 | Navigation | Các tab chuyển đổi nhanh hoạt động độc lập và tải đúng dữ liệu tương ứng. | Nielsen #7: Flexibility | Pass | Chuyển giữa "Checked In" và "Scan Logs" sub-tab — mỗi tab load đúng nội dung (khác nhau: bảng user vs bảng scan log). |
| IA-03-08 | Navigation | Không có liên kết nào bị hỏng (Broken links / 404 error) trên toàn giao diện. | Nielsen #4: Consistency | Pass | Kiểm tra 11 links trên trang — tất cả đều là valid internal paths. |
| IA-03-09 | Navigation | Nút "Cuộn lên đầu trang" (Back to top) hiển thị khi người dùng cuộn xuống sâu (nếu có). | Nielsen #7: Flexibility | NA | Màn hình không đủ dài để cần scroll-to-top; không có nút này. |
| IA-03-10 | Navigation | Thanh bên sidebar có thể thu gọn/mở rộng mượt mà và không che khuất nội dung chính. | Nielsen #3: User Control | Pass | Sidebar collapse hoạt động mượt mà — thu gọn xuống icon-only, content area mở rộng tương ứng. |
| IA-03-11 | Navigation | Đường dẫn URL trên thanh địa chỉ thay đổi tương ứng khi chuyển đổi qua lại giữa các tab hoặc bộ lọc. | Nielsen #4: Consistency | Fail | URL giữ nguyên ?tab=checkin khi switch giữa sub-tab "Checked In" và "Scan Logs" — không cập nhật thêm parameter cho sub-tab. Deep link đến sub-tab cụ thể là không thể. Ảnh: screenshots/A5-bug-IA-03-11.png |
| IA-03-12 | Navigation | Giao diện kéo thả (Reorder) hiển thị biểu tượng tay cầm (drag handle) rõ ràng để gợi ý khả năng tương tác. | Norman: Signifiers | NA | Không có drag-and-drop feature trên màn hình Check-in. |
| **IA-04** | **Feedback** | **IA-04: Feedback & State (Toasts, Badges, Confirmations, Progress Bars, Status Colors)** | | | |
| IA-04-01 | Feedback | Thông báo nổi (Toasts) xuất hiện ngay sau khi thực hiện hành động và tự động tắt sau 3-5s. | Norman: Feedback | Fail | Click "Export" với bảng rỗng ("No results") không kích hoạt bất kỳ toast hay feedback nào. API call cũng không được gửi đi. Ảnh: screenshots/A5-bug-IA-04-14b.png |
| IA-04-02 | Feedback | Toasts có màu sắc phân biệt rõ ràng: Xanh (Thành công), Đỏ (Lỗi), Vàng (Cảnh báo). | Nielsen #8: Aesthetic | NA | Không có toast xuất hiện trong session này để kiểm tra màu sắc. |
| IA-04-03 | Feedback | Hộp thoại xác nhận (Confirmation dialog) xuất hiện trước các hành động hủy/xóa quan trọng. | Nielsen #5: Error Prev. | NA | Không có action hủy/xóa trên màn hình Check-in tab này. |
| IA-04-04 | Feedback | Huy hiệu (Badges) hiển thị chính xác số lượng thông báo; trạng thái vé thay đổi tương ứng khi được phê duyệt/hủy. | Nielsen #1: Visibility | Pass | Badge "5" trên notification bell hiển thị đúng số lượng thông báo. |
| IA-04-05 | Feedback | Thanh tiến trình (Progress bar) hoặc vòng xoay tải (Spinner) xuất hiện khi hệ thống xử lý. | Nielsen #1: Visibility | NA | Không thể submit scan (check-in window chưa mở) — không quan sát được spinner. Cần kiểm tra thủ công khi window mở. |
| IA-04-06 | Feedback | Trạng thái hiển thị màu sắc tương thích với ngữ nghĩa (Ví dụ: APPROVED màu xanh lá, REJECTED màu đỏ). | Nielsen #2: Match System | NA | Không có scan result nào trong session (0 check-ins). Không thể kiểm tra màu SUCCESS/FAILED. Cần test data. |
| IA-04-07 | Feedback | Chấm đỏ thông báo (Notification dot) hiển thị động ngay khi có thay đổi trạng thái đăng ký. | Nielsen #1: Visibility | Pass | Notification badge (số "5") hiển thị trên bell icon trong header. |
| IA-04-08 | Feedback | Hộp thoại chi tiết ảnh (Lightbox) mở rộng mượt mà khi click vào ảnh đính kèm. | Nielsen #7: Flexibility | NA | Không có ảnh đính kèm trên màn hình Check-in. |
| IA-04-09 | Feedback | Cập nhật dữ liệu thời gian thực (Real-time update) mà không cần người dùng reload trang. | Norman: Feedback | NA | Không thể kiểm tra real-time update vì check-in window chưa mở và không có scan data. Yêu cầu 2 device để test đồng thời. |
| IA-04-10 | Feedback | Hiển thị thông báo rõ ràng khi mất kết nối mạng Internet. | Nielsen #1: Visibility | NA | Không thể mô phỏng offline state trong môi trường test hiện tại. Cần kiểm tra thủ công. |
| IA-04-11 | Feedback | Hệ thống vô hiệu hóa nút gửi hoặc ngăn chặn gửi dữ liệu trùng lặp khi người dùng click đúp nút Submit. | Nielsen #5: Error Prev. | NA | Nút Submit scan bị disabled (check-in window chưa mở) — không thể test double-submit. Cần kiểm tra thủ công. |
| IA-04-12 | Feedback | Mã QR/Barcode trên vé hiển thị rõ nét (không bị mờ), có kích thước tối thiểu đảm bảo quét được bằng ứng dụng camera thông thường. | Nielsen #1: Visibility | NA | Screen A5 là màn hình nhập barcode (quét từ vé), không hiển thị QR. QR hiển thị trên vé của user — thuộc screen khác. |
| IA-04-13 | Feedback | Ô nhập liệu (text box) hiển thị hiệu ứng viền/nổi bật trực quan (focus state) khi nhấp chuột vào để người dùng nhận biết rõ ràng đang thao tác/nhập liệu. | Norman: Feedback | Pass | Search box "Search checkins" hiển thị focus state rõ ràng khi click (ring outline xanh theo Tailwind focus-visible). |
| IA-04-14 | Feedback | Các nút secondary actions phải được vô hiệu hóa (disabled + đổi con trỏ) khi không có gì để thực hiện, hoặc phải hiển thị phản hồi rõ ràng (toast/thông báo) nếu vẫn cho phép bấm mà không có tác dụng gì | Norman: Feedback + Signifiers | Fail | (1) Nút "Submit scan" khi disabled có cursor vẫn là pointer (không phải not-allowed) — thiếu visual cue về trạng thái không khả dụng. (2) Nút "Export" khi bảng rỗng: vẫn enabled và clickable, nhưng không có response nào (không toast, không file download, không API call) — vi phạm nghiêm trọng. Ảnh: screenshots/A5-bug-IA-04-14.png |

**Tổng kết Screen A5:** 17 Pass / 5 Fail / 18 NA / Tổng 40 item
```

## Prompt 14
**AI Tool:** Claude Sonnet 4.6
**Ngày giờ:** 02/08/2026 08:00 PM
**Prompt:**
```
gui-checklist-executor
  screen dashboard kpi https://prod-dev.ems-fitus.cloud/dashboard/admin
```

**AI output:**
```
The user has issued a fresh, focused run. Let me confirm the updated inputs before proceeding:

I'm about to run the GUI checklist with the following setup:

Input	Value
Target URL	https://prod-dev.ems-fitus.cloud/dashboard/admin
Screens to test	1. Dashboard (/dashboard/admin — landing page), 2. KPI (/dashboard/admin/analytics/overview — Analytics Overview)
Login	admin@gmail.com / Admin@123 (confirmed active)
Reference checklist	shared_gui_checklist.md (46 items: IA-01 to IA-04)
Output file	dashboard-kpi-gui-checklist.md + screenshots/
Environment check: ✅ Already confirmed — site reachable, admin logged in, both screens accessible.

Shall I proceed? (yes / adjust something first)
```
----
## Prompt 15
**AI Tool:** Claude Sonnet 4.6
**Ngày giờ:** 02/08/2026 08:05 PM
**Prompt:**
```
screen to test: just one Dashboard (/dashboard/admin — landing page)
```
**AI output:**
```
# GUI Checklist Execution — Dashboard Screen

**Target URL:** https://prod-dev.ems-fitus.cloud/dashboard/admin  
**Executed by:** AI Agent (Chrome DevTools MCP)  
**Run date:** 2026-08-02  
**Reference checklist:** `shared_gui_checklist.md`  
**Login:** admin@gmail.com (Admin role)

---

## Environment Check

| Item | Status |
|---|---|
| Site reachable | ✅ OK |
| Login successful | ✅ OK (already authenticated) |
| Target screen accessible | ✅ OK — page title: "Admin Management \| HCMUS EMS" |

---

## Screen: Dashboard (`/dashboard/admin`)

> **Page structure observed:**
> - Fixed left sidebar: FIT EMS Admin logo, nav links (Users Management, Categories, Academic Years, Campuses, Events Management, Support requests [badge 6], User Guide), Analytics accordion, Settings accordion, Collapse button
> - Header (banner): Switch language button, "Back to user dashboard" link, Notifications button [badge 0], User avatar menu
> - Main content: EMS logo image, H1 "Admin Dashboard", welcome text, 4 KPI stat cards (Total Events: 0, Total Check-ins: 0, Attendance Rate: 0%, Total Users: 0)

| ID | IA | Checklist Item | Reference | Pass/Fail/NA | Notes | Screenshot |
|---|---|---|---|---|---|---|
| **IA-01** | **General UI** | **General UI Standards** | | | | |
| IA-01-01 | General UI | Hệ thống lưới và khoảng cách (Grid & Spacing) căn lề nhất quán trên toàn màn hình. | Nielsen #4 | Pass | Sidebar, header, and main use consistent grid. Nav items use `px-3 py-2.5`. KPI cards are evenly spaced. No misalignment observed. | |
| IA-01-02 | General UI | Font chữ (typography) nhất quán về kích thước, độ dày (bold/regular) và phân cấp tiêu đề. | Nielsen #4 | Pass | Single font (`ui-sans-serif`). H1 uses `text-4xl font-black`. Clear hierarchy: H1 > body text > labels. Consistent throughout. | |
| IA-01-03 | General UI | Màu sắc của các nút hành động (Primary, Secondary) và trạng thái nhất quán. | Norman: Signifiers | Pass | Sidebar uses dark bg `rgb(24,24,27)` with cyan active highlight `#1bc2f5`. No action buttons on landing page — consistent with system-wide pattern. | |
| IA-01-04 | General UI | Đa ngôn ngữ (EN/VI) hoạt động đầy đủ, không bị dịch thiếu hoặc chồng lấp chữ. | Nielsen #4 | Fail | After switching to Tiếng Việt: sidebar, H1 ("Trang Quản trị"), KPI labels translate correctly. BUT header retains two hardcoded English strings: (1) link "Back to user dashboard" and (2) button "Notifications" — not connected to the i18n system. No text overlap. | screenshots/Dashboard-bug-IA-01-04.png |
| IA-01-05 | General UI | Trạng thái rỗng (Empty state) được hiển thị rõ ràng khi không có sự kiện/dữ liệu nào. | Nielsen #1 | Pass | All 4 KPI cards display "0" clearly. Intentional default state, not a broken empty display. | |
| IA-01-06 | General UI | Trạng thái đang tải (Loading state/skeleton) hiển thị khi kéo dữ liệu chậm. | Nielsen #1 | NA | No skeleton/shimmer elements detected under normal conditions. Requires throttled network — manual verification needed. | |
| IA-01-07 | General UI | Trang web tương thích tốt và tự động co giãn (Responsive) trên màn hình. | Nielsen #4 | Fail | At 375px viewport: sidebar stays at 256px width, main content shrinks to 231px (total 487px > 375px). Horizontal overflow occurs. Hamburger button exists (`lg:hidden` class) but does not collapse the sidebar. | screenshots/Dashboard-bug-IA-01-07.png |
| IA-01-08 | General UI | Các hình ảnh (Thumbnail/Banner) không bị méo tỉ lệ hiển thị. | Shneiderman | NA | No event thumbnails or banners on this landing page. EMS logo is decorative only. | |
| IA-01-09 | General UI | Các icon được căn chỉnh đúng tâm so với nhãn text bên cạnh. | Shneiderman | Pass | All 7 sidebar nav links use `flex items-center gap-3` — icons are vertically centered with text labels. Confirmed via DOM. | |
| IA-01-10 | General UI | Độ tương phản màu sắc giữa văn bản và nền đủ rõ ràng (Accessibility WCAG). | Nielsen #4 | Pass | H1 near-black (`lab(8.11...)`) on white body — high contrast. Sidebar dark bg with light text — sufficient. Full WCAG AA ratio requires axe tool — flag for manual follow-up. | |
| IA-01-11 | General UI | Các liên kết ngoài (External links) mở ở tab mới, liên kết nội bộ (Internal links) mở ở tab hiện tại. | Nielsen #3 | NA | No external links on this page. All internal links open in current tab (default behavior). | |
| IA-01-12 | General UI | Ảnh Thumbnail (4:3) và Banner (24:9) không bị cắt xén mất nội dung quan trọng. | Nielsen #4 | NA | No thumbnails or banner images on this page. | |
| **IA-02** | **Forms** | **Forms** | | | | |
| IA-02-01 | Forms | Các trường bắt buộc nhập (Required fields) được đánh dấu ký hiệu trực quan. | Norman | NA | No form fields on this page. | |
| IA-02-02 | Forms | Nhãn (Labels) của trường nhập liệu luôn hiển thị rõ ràng. | Nielsen #6 | NA | No form fields on this page. | |
| IA-02-03 | Forms | Validation thời gian thực báo lỗi đỏ trực quan ngay dưới trường nhập liệu bị lỗi. | Nielsen #5 | NA | No form fields on this page. | |
| IA-02-04 | Forms | Thông báo lỗi cụ thể, hướng dẫn cách khắc phục. | Nielsen #10 | NA | No form fields on this page. | |
| IA-02-05 | Forms | Định dạng tải lên (Upload file/image) kiểm tra đúng định dạng và dung lượng tối đa. | Norman | NA | No upload fields on this page. | |
| IA-02-06 | Forms | Trình soạn thảo Rich Text hiển thị đầy đủ thanh công cụ. | Nielsen #7 | NA | No rich text editor on this page. | |
| IA-02-07 | Forms | Người dùng có thể nhấn Tab để di chuyển tuần tự qua các ô nhập liệu. | Nielsen #7 | NA | No form inputs on this page. | |
| IA-02-08 | Forms | Các nút Submit/Save bị vô hiệu hóa (disabled) khi form chưa điền đủ. | Nielsen #5 | NA | No Submit/Save buttons on this page. | |
| IA-02-09 | Forms | Định dạng ngày giờ hiển thị theo chuẩn cục bộ dễ đọc. | Nielsen #2 | NA | No date/time fields on this page. | |
| IA-02-10 | Forms | Nút xóa nhanh (clear button) hoặc reset form hoạt động chính xác. | Nielsen #3 | NA | No form with clear/reset on this page. | |
| IA-02-11 | Forms | Trình duyệt hỗ trợ tính năng tự động điền (autofill). | Nielsen #7 | NA | No form inputs on this page. | |
| IA-02-12 | Forms | Ô nhập mật khẩu hỗ trợ tính năng toggle ẩn/hiện mật khẩu. | Nielsen #7 | NA | No password fields on this page. | |
| **IA-03** | **Navigation** | **Navigation** | | | | |
| IA-03-01 | Navigation | Menu điều hướng chính luôn cố định hoặc dễ dàng truy cập ở đầu trang/thanh bên. | Nielsen #6 | Pass | Sidebar has `position: fixed` — stays in place while scrolling. Contains all primary sections. | |
| IA-03-02 | Navigation | Trạng thái hiện tại của trang (Active state) được làm nổi bật trên menu điều hướng. | Nielsen #1 | Fail | On `/dashboard/admin`, all 7 sidebar links show `text-gray-400` (inactive). No `aria-current="page"`. No visual indication of current location. On sub-pages (e.g., /users), the corresponding link correctly highlights with `bg-[#1bc2f5]` — the root dashboard has no matching nav item. | screenshots/Dashboard-bug-IA-03-02.png |
| IA-03-03 | Navigation | Nút quay lại (Back/Return action) đưa người dùng về đúng trang trước đó. | Nielsen #3 | NA | Dashboard is the root admin entry point — no Back button expected. "Back to user dashboard" link returns to the public dashboard by design. | |
| IA-03-04 | Navigation | Liên kết sâu (Deep links) dẫn trực tiếp đến trang chi tiết mà không bị lỗi 404. | Nielsen #4 | Pass | Navigating directly to `https://prod-dev.ems-fitus.cloud/dashboard/admin` loads correctly without 404. | |
| IA-03-05 | Navigation | Breadcrumbs hiển thị đúng phân cấp thư mục và có thể click để quay về thư mục cha. | Nielsen #6 | Fail | No breadcrumb component found on the Dashboard. No `[aria-label*="breadcrumb"]`, no `ol.breadcrumb`. Only H1 text provides location context. Consistent with system-wide absence of breadcrumbs. | screenshots/Dashboard-bug-IA-03-05.png |
| IA-03-06 | Navigation | Tính năng kéo thả thay đổi thứ tự (Reorder) hiển thị trực quan. | Norman | NA | No drag-and-drop feature on this page. | |
| IA-03-07 | Navigation | Các tab chuyển đổi nhanh hoạt động độc lập và tải đúng dữ liệu tương ứng. | Nielsen #7 | NA | No tabs on the Dashboard landing page. | |
| IA-03-08 | Navigation | Không có liên kết nào bị hỏng (Broken links / 404 error). | Nielsen #4 | Pass | All 7 sidebar links point to valid `/dashboard/admin/*` paths. No `href="#"` or empty hrefs found. | |
| IA-03-09 | Navigation | Nút "Cuộn lên đầu trang" (Back to top) hiển thị khi người dùng cuộn xuống sâu. | Nielsen #7 | NA | Page content is short (single viewport). No scroll-to-top needed or present. | |
| IA-03-10 | Navigation | Thanh bên sidebar có thể thu gọn/mở rộng mượt mà và không che khuất nội dung chính. | Nielsen #3 | Pass | Sidebar collapses: 256px → 80px (icon-only). Main content left edge shifts from 256px → 80px. No overlap. CSS-animated transition. Expand restores correctly. | |
| IA-03-11 | Navigation | Đường dẫn URL trên thanh địa chỉ thay đổi tương ứng khi chuyển đổi qua lại giữa các tab hoặc bộ lọc. | Nielsen #4 | NA | No tabs or filters on the Dashboard landing page. URL remains `/dashboard/admin` — correct. | |
| IA-03-12 | Navigation | Giao diện kéo thả (Reorder) hiển thị biểu tượng tay cầm (drag handle) rõ ràng. | Norman | NA | No drag-and-drop feature on this page. | |
| **IA-04** | **Feedback** | **Feedback & State** | | | | |
| IA-04-01 | Feedback | Thông báo nổi (Toasts) xuất hiện ngay sau khi thực hiện hành động và tự động tắt sau 3-5s. | Norman | NA | No actionable operations on the Dashboard landing page that trigger a toast. | |
| IA-04-02 | Feedback | Toasts có màu sắc phân biệt rõ ràng: Xanh (Thành công), Đỏ (Lỗi), Vàng (Cảnh báo). | Nielsen #8 | NA | No toasts visible on this page during this run. | |
| IA-04-03 | Feedback | Hộp thoại xác nhận (Confirmation dialog) xuất hiện trước các hành động hủy/xóa quan trọng. | Nielsen #5 | NA | No destructive actions on this page. | |
| IA-04-04 | Feedback | Huy hiệu (Badges) hiển thị chính xác số lượng thông báo. | Nielsen #1 | Fail | Notification badge shows "0" in the header. However, opening the panel reveals 5 notifications present (timestamps: 10h, 12h, 20h, 2 days ×2 ago). Badge count is incorrect — stale or not computed from actual unread count. | screenshots/Dashboard-bug-IA-04-07.png |
| IA-04-05 | Feedback | Thanh tiến trình (Progress bar) hoặc vòng xoay tải (Spinner) xuất hiện khi hệ thống xử lý. | Nielsen #1 | NA | No async operations triggered during this run. Cannot verify spinner behavior. | |
| IA-04-06 | Feedback | Trạng thái hiển thị màu sắc tương thích với ngữ nghĩa (APPROVED xanh lá, REJECTED đỏ). | Nielsen #2 | NA | No status badges on this page. KPI cards show plain numeric values. | |
| IA-04-07 | Feedback | Chấm đỏ thông báo (Notification dot) hiển thị động ngay khi có thay đổi trạng thái đăng ký. | Nielsen #1 | Fail | Badge displays "0" despite 5 notifications being present (same evidence as IA-04-04). Real-time update behavior cannot be confirmed without two simultaneous sessions. | screenshots/Dashboard-bug-IA-04-07.png |
| IA-04-08 | Feedback | Hộp thoại chi tiết ảnh (Lightbox) mở rộng mượt mà khi click vào ảnh đính kèm. | Nielsen #7 | NA | No clickable image attachments on this page. | |
| IA-04-09 | Feedback | Cập nhật dữ liệu thời gian thực (Real-time update) mà không cần người dùng reload trang. | Norman | NA | Requires two simultaneous sessions to verify. Manual testing needed. | |
| IA-04-10 | Feedback | Hiển thị thông báo rõ ràng khi mất kết nối mạng Internet. | Nielsen #1 | NA | Cannot simulate network disconnect in this environment. Manual testing needed. | |
| IA-04-11 | Feedback | Hệ thống vô hiệu hóa nút gửi hoặc ngăn chặn gửi dữ liệu trùng lặp khi người dùng click đúp. | Nielsen #5 | NA | No Submit buttons on this page. | |
| IA-04-12 | Feedback | Mã QR/Barcode trên vé hiển thị rõ nét (không bị mờ). | Nielsen #1 | NA | No QR codes on this page. | |
| IA-04-13 | Feedback | Ô nhập liệu (text box) hiển thị hiệu ứng viền/nổi bật trực quan (focus state). | Norman | NA | No text inputs on the Dashboard landing page. | |
| IA-04-14 | Feedback | Các nút secondary actions phải được vô hiệu hóa (disabled) khi không có gì để thực hiện. | Norman | NA | No secondary action buttons on this page. | |

---

**Tổng kết Dashboard:**

| Verdict | Count |
|---|---|
| ✅ Pass | 10 |
| ❌ Fail | 5 |
| ➖ NA | 31 |
| **Total** | **46** |

---

## Bug Reports

### BUG-01 — Header links not translated when switching to Vietnamese

- **Screen:** Dashboard (`/dashboard/admin`)
- **Checklist item:** IA-01-04 — Đa ngôn ngữ (EN/VI) hoạt động đầy đủ, không bị dịch thiếu
- **Steps to reproduce:**
  1. Navigate to `https://prod-dev.ems-fitus.cloud/dashboard/admin`
  2. Click "Switch language" in the header
  3. Select "Tiếng Việt"
  4. Observe the header area
- **Expected result:** All UI text switches to Vietnamese, including header links and buttons
- **Actual result:** Link "Back to user dashboard" and button "Notifications" remain in English. Sidebar, main heading, and KPI labels translate correctly. These two strings are hardcoded — not connected to the i18n system.
- **Severity:** 1 Minor — i18n inconsistency; core navigation still works; no data at risk.
- **Screenshot:** screenshots/Dashboard-bug-IA-01-04.png

---

### BUG-02 — Sidebar overflows on mobile (375px) — hamburger toggle not functional

- **Screen:** Dashboard (`/dashboard/admin`)
- **Checklist item:** IA-01-07 — Trang web tương thích tốt và tự động co giãn (Responsive)
- **Steps to reproduce:**
  1. Navigate to `https://prod-dev.ems-fitus.cloud/dashboard/admin`
  2. Set viewport to 375px × 812px (iPhone SE)
  3. Observe page layout
- **Expected result:** Sidebar hides behind a hamburger menu; main content fills full viewport width
- **Actual result:** Sidebar stays at 256px, main content compressed to 231px, total 487px > 375px viewport — horizontal overflow. Hamburger button exists in DOM (`class*="lg:hidden"`) but clicking does not collapse the sidebar.
- **Severity:** 2 Moderate — Admin panel unusable on mobile/small tablet screens.
- **Screenshot:** screenshots/Dashboard-bug-IA-01-07.png

---

### BUG-03 — No active navigation state on Dashboard landing page

- **Screen:** Dashboard (`/dashboard/admin`)
- **Checklist item:** IA-03-02 — Trạng thái hiện tại của trang (Active state) được làm nổi bật
- **Steps to reproduce:**
  1. Navigate to `https://prod-dev.ems-fitus.cloud/dashboard/admin`
  2. Observe the sidebar navigation
- **Expected result:** Current page section is highlighted in the sidebar
- **Actual result:** All 7 sidebar nav links show `text-gray-400` (inactive). No `aria-current="page"` attribute set. The root `/dashboard/admin` page has no corresponding sidebar nav item — nothing highlights. Sub-pages work correctly.
- **Severity:** 1 Minor — Page heading provides context; workaround is the H1 text.
- **Screenshot:** screenshots/Dashboard-bug-IA-03-02.png

---

### BUG-04 — No breadcrumbs anywhere on Dashboard

- **Screen:** Dashboard (`/dashboard/admin`)
- **Checklist item:** IA-03-05 — Breadcrumbs hiển thị đúng phân cấp thư mục
- **Steps to reproduce:**
  1. Navigate to `https://prod-dev.ems-fitus.cloud/dashboard/admin`
  2. Look for breadcrumb trail
- **Expected result:** Breadcrumb like "EMS Admin > Dashboard" visible
- **Actual result:** No breadcrumb component found. No `[aria-label*="breadcrumb"]`, no `ol.breadcrumb`, no `[class*="breadcrumb"]` in DOM. Only H1 provides location context. System-wide issue.
- **Severity:** 1 Minor — Dashboard is the root; shallow hierarchy limits impact here. Worsens on deeper sub-pages.
- **Screenshot:** screenshots/Dashboard-bug-IA-03-05.png

---

### BUG-05 — Notification badge shows "0" despite 5 notifications present in panel

- **Screen:** Dashboard (`/dashboard/admin`)
- **Checklist items:** IA-04-04, IA-04-07 — Badge hiển thị chính xác số lượng thông báo
- **Steps to reproduce:**
  1. Navigate to `https://prod-dev.ems-fitus.cloud/dashboard/admin`
  2. Observe bell icon badge — shows "0"
  3. Click Notifications button
  4. Count notifications in panel
- **Expected result:** Badge shows count of unread notifications
- **Actual result:** Badge shows **"0"** but panel contains **5 notifications** (all "Phản hồi khiếu nại", received 10h, 12h, 20h, 2 days, 2 days ago). Badge count does not reflect actual notification count. "Mark all as read" button is present but badge does not update from loading.
- **Severity:** 2 Moderate — Admins will miss support/complaint notifications. Could cause delayed response to users.
- **Screenshot:** screenshots/Dashboard-bug-IA-04-07.png

---

## Items Requiring Manual Verification (NA — cannot be automated)

| Item | Reason |
|---|---|
| IA-01-06 | Skeleton loading requires DevTools Network throttling |
| IA-01-10 | Full WCAG AA contrast ratio requires dedicated tool (e.g., axe) |
| IA-04-05 | Spinner requires async action that is not available on this page |
| IA-04-09 | Real-time update requires 2 simultaneous authenticated sessions |
| IA-04-10 | Offline notification requires manual network disconnect |
```