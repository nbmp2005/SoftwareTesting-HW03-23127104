# Task 1B — Checklist Execution (Individual)
---

## Screen A4: Participants & Reviews approval

| ID | Khía Cạnh | Mục Kiểm Tra (Checklist Item Description) | Ánh Xạ Heuristics / Nguyên Tắc | Screen A4 (Pass/Fail/NA) | Ghi Chú Lỗi (Notes) |
|---|---|---|---|---|---|
| **IA-01** | **General UI** | **IA-01: General UI Standards (Layout, Typography, Color, Consistency, i18n)** | | | | |
| IA-01-01 | General UI | Hệ thống lưới và khoảng cách (Grid & Spacing) căn lề nhất quán trên toàn màn hình. | Nielsen #4: Consistency | Pass | |
| IA-01-02 | General UI | Font chữ (typography) nhất quán về kích thước, độ dày (bold/regular) và phân cấp tiêu đề. | Nielsen #4: Consistency | Pass | |
| IA-01-03 | General UI | Màu sắc của các nút hành động (Primary, Secondary) và trạng thái nhất quán. | Norman: Signifiers | Pass | |
| IA-01-04 | General UI | Đa ngôn ngữ (EN/VI) hoạt động đầy đủ, không bị dịch thiếu hoặc chồng lấp chữ. | Nielsen #4: Consistency | Fail | Role name chuyển sang tiếng anh vẫn là "học viên tham dự" |
| IA-01-05 | General UI | Trạng thái rỗng (Empty state) được hiển thị rõ ràng khi không có sự kiện/dữ liệu nào. | Nielsen #1: Visibility | Pass | |
| IA-01-06 | General UI | Trạng thái đang tải (Loading state/skeleton) hiển thị khi kéo dữ liệu chậm. | Nielsen #1: Visibility | Fail | Không có hiệu ứng loading  |
| IA-01-07 | General UI | Trang web tương thích tốt và tự động co giãn (Responsive) trên màn hình. | Nielsen #4: Consistency | Fail | Trang không được responsive |
| IA-01-08 | General UI | Các hình ảnh (Thumbnail/Banner) không bị méo tỉ lệ hiển thị (tỷ lệ 4:3 và 24:9) trên các kích thước màn hình khác nhau. | Shneiderman: Aesthetics | Pass | |
| IA-01-09 | General UI | Các icon được căn chỉnh đúng tâm so với nhãn text bên cạnh. | Shneiderman: Aesthetics | Pass | | | |
| IA-01-10 | General UI | Độ tương phản màu sắc giữa văn bản và nền đủ rõ ràng (Accessibility WCAG). | Nielsen #4: Consistency | Pass | | | |
| IA-01-11 | General UI | Các liên kết ngoài (External links) mở ở tab mới, liên kết nội bộ (Internal links) mở ở tab hiện tại. | Nielsen #3: User Control | NA | | | |
| IA-01-12 | General UI | Ảnh Thumbnail (4:3) và Banner (24:9) không bị cắt xén mất nội dung quan trọng. | Nielsen #4: Consistency | NA | |
| **IA-02** | **Forms** | **IA-02: Forms (Labels, Validation, Errors, Required Fields, Rich Text)** | | | | | |
| IA-02-01 | Forms | Các trường bắt buộc nhập (Required fields) được đánh dấu ký hiệu trực quan (ví dụ dấu `*`). | Norman: Constraints | NA | |
| IA-02-02 | Forms | Nhãn (Labels) của trường nhập liệu luôn hiển thị rõ ràng và đi sát với ô nhập liệu. | Nielsen #6: Recognition | Pass | |
| IA-02-03 | Forms | Validation thời gian thực báo lỗi đỏ trực quan ngay dưới trường nhập liệu bị lỗi. | Nielsen #5: Error Prev. | NA | | | |
| IA-02-04 | Forms | Thông báo lỗi cụ thể, hướng dẫn cách khắc phục thay vì báo lỗi chung chung. | Nielsen #10: Help & Error |  NA | | | |
| IA-02-05 | Forms | Định dạng tải lên (Upload file/image) kiểm tra đúng định dạng và dung lượng tối đa. | Norman: Constraints | NA | | | |
| IA-02-06 | Forms | Trình soạn thảo Rich Text hiển thị đầy đủ thanh công cụ và hoạt động mượt mà. | Nielsen #7: Flexibility | NA | | | |
| IA-02-07 | Forms | Người dùng có thể nhấn `Tab` để di chuyển tuần tự qua các ô nhập liệu trong form. | Nielsen #7: Flexibility | NA | | | |
| IA-02-08 | Forms | Các nút Submit/Save bị vô hiệu hóa (disabled) khi form chưa điền đủ thông tin hợp lệ. | Nielsen #5: Error Prev. | NA | | | |
| IA-02-09 | Forms | Định dạng ngày giờ hiển thị theo chuẩn cục bộ dễ đọc đối với người dùng Việt Nam. | Nielsen #2: Match System | NA | | | |
| IA-02-10 | Forms | Nút xóa nhanh (clear button) hoặc reset form hoạt động chính xác. | Nielsen #3: User Control | NA | | | |
| IA-02-11 | Forms | Trình duyệt hỗ trợ tính năng tự động điền (autofill) cho các trường thông tin cơ bản. | Nielsen #7: Flexibility | NA | | | |
| IA-02-12 | Forms | Ô nhập mật khẩu hỗ trợ tính năng toggle ẩn/hiện mật khẩu trực quan bằng biểu tượng con mắt. | Nielsen #7: Flexibility | NA | | | |
| **IA-03** | **Navigation** | **IA-03: Navigation (Menus, Breadcrumbs, Sidebar, Tabs, Back actions, Deep links)** | | | | | |
| IA-03-01 | Navigation | Menu điều hướng chính luôn cố định hoặc dễ dàng truy cập ở đầu trang/thanh bên. | Nielsen #6: Recognition | Pass | | | |
| IA-03-02 | Navigation | Trạng thái hiện tại của trang (Active state) được làm nổi bật trên menu điều hướng. | Nielsen #1: Visibility | Pass | | | |
| IA-03-03 | Navigation | Nút quay lại (Back/Return action) đưa người dùng về đúng trang trước đó, không mất trạng thái. | Nielsen #3: User Control | Fail | Khi thay đổi số dòng hiển thị thành 50 dòng, truy cập vào trang chi tiết sự kiện rồi bấm Quay lại (Back), hệ thống không lưu giữ trạng thái phân trang mà tự động reset số dòng hiển thị về 5 dòng. | | |
| IA-03-04 | Navigation | Liên kết sâu (Deep links) dẫn trực tiếp đến trang chi tiết sự kiện mà không bị lỗi 404. | Nielsen #4: Consistency | Pass | | | |
| IA-03-05 | Navigation | Breadcrumbs hiển thị đúng phân cấp thư mục và có thể click để quay về thư mục cha. | Nielsen #6: Recognition | NA | | | |
| IA-03-06 | Navigation | Tính năng kéo thả thay đổi thứ tự (Reorder) hiển thị trực quan (dòng bị kéo mờ opacity-50) và các nút thao tác khác tạm thời bị vô hiệu hóa. | Norman: Feedback | NA | | | |
| IA-03-07 | Navigation | Các tab chuyển đổi nhanh hoạt động độc lập và tải đúng dữ liệu tương ứng. | Nielsen #7: Flexibility | Pass | | | |
| IA-03-08 | Navigation | Không có liên kết nào bị hỏng (Broken links / 404 error) trên toàn giao diện. | Nielsen #4: Consistency | Pass | | | |
| IA-03-09 | Navigation | Nút "Cuộn lên đầu trang" (Back to top) hiển thị khi người dùng cuộn xuống sâu (nếu có). | Nielsen #7: Flexibility | NA | | | |
| IA-03-10 | Navigation | Thanh bên sidebar có thể thu gọn/mở rộng mượt mà và không che khuất nội dung chính. | Nielsen #3: User Control | Pass | | | |
| IA-03-11 | Navigation | Đường dẫn URL trên thanh địa chỉ thay đổi tương ứng khi chuyển đổi qua lại giữa các tab hoặc bộ lọc. | Nielsen #4: Consistency | Pass | | | |
| IA-03-12 | Navigation | Giao diện kéo thả (Reorder) hiển thị biểu tượng tay cầm (drag handle) rõ ràng để gợi ý khả năng tương tác. | Norman: Signifiers | NA | | | |
| **IA-04** | **Feedback** | **IA-04: Feedback & State (Toasts, Badges, Confirmations, Progress Bars, Status Colors)** | | | | | |
| IA-04-01 | Feedback | Thông báo nổi (Toasts) xuất hiện ngay sau khi thực hiện hành động và tự động tắt sau 3-5s. | Norman: Feedback | Pass | | | |
| IA-04-02 | Feedback | Toasts có màu sắc phân biệt rõ ràng: Xanh (Thành công), Đỏ (Lỗi), Vàng (Cảnh báo). | Nielsen #8: Aesthetic | Pass | | | |
| IA-04-03 | Feedback | Hộp thoại xác nhận (Confirmation dialog) xuất hiện trước các hành động hủy/xóa quan trọng. | Nielsen #5: Error Prev. | Pass | | | |
| IA-04-04 | Feedback | Huy hiệu (Badges) hiển thị chính xác số lượng thông báo; trạng thái vé thay đổi tương ứng khi được phê duyệt/hủy. | Nielsen #1: Visibility | Pass | | | |
| IA-04-05 | Feedback | Thanh tiến trình (Progress bar) hoặc vòng xoay tải (Spinner) xuất hiện khi hệ thống xử lý. | Nielsen #1: Visibility | Pass | | | |
| IA-04-06 | Feedback | Trạng thái hiển thị màu sắc tương thích với ngữ nghĩa (Ví dụ: APPROVED màu xanh lá, REJECTED màu đỏ). | Nielsen #2: Match System | Pass | | | |
| IA-04-07 | Feedback | Chấm đỏ thông báo (Notification dot) hiển thị động ngay khi có thay đổi trạng thái đăng ký. | Nielsen #1: Visibility | Pass | | | |
| IA-04-08 | Feedback | Hộp thoại chi tiết ảnh (Lightbox) mở rộng mượt mà khi click vào ảnh đính kèm. | Nielsen #7: Flexibility | NA | | | |
| IA-04-09 | Feedback | Cập nhật dữ liệu thời gian thực (Real-time update) mà không cần người dùng reload trang. | Norman: Feedback | Pass | | | |
| IA-04-10 | Feedback | Hiển thị thông báo rõ ràng khi mất kết nối mạng Internet. | Nielsen #1: Visibility | Fail | Trang bị đứng nhưng không hiển thị thông báo | | |
| IA-04-11 | Feedback | Hệ thống vô hiệu hóa nút gửi hoặc ngăn chặn gửi dữ liệu trùng lặp khi người dùng click đúp nút Submit. | Nielsen #5: Error Prev. | NA | | | |
| IA-04-12 | Feedback | Mã QR/Barcode trên vé hiển thị rõ nét (không bị mờ), có kích thước tối thiểu đảm bảo quét được bằng ứng dụng camera thông thường. | Nielsen #1: Visibility | NA | | | |
| IA-04-13 | Feedback | Ô nhập liệu (text box) hiển thị hiệu ứng viền/nổi bật trực quan (focus state) khi nhấp chuột vào để người dùng nhận biết rõ ràng đang thao tác/nhập liệu. | Norman: Feedback | Pass | | | |
| IA-04-14 | Feedback | Các nút secondary actions phải được vô hiệu hóa (disabled + đổi con trỏ) khi không có gì để thực hiện, hoặc phải hiển thị phản hồi rõ ràng (toast/thông báo) nếu vẫn cho phép bấm mà không có tác dụng gì | Norman: Feedback + Signifiers | Fail | Nút Cancel All không bị disable dù không có tác dụng hay thực hiện thao tác gì


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
| IA-01-04 | General UI | Đa ngôn ngữ (EN/VI) hoạt động đầy đủ, không bị dịch thiếu hoặc chồng lấp chữ. | Nielsen #4: Consistency | Pass | |
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
| IA-03-05 | Navigation | Breadcrumbs hiển thị đúng phân cấp thư mục và có thể click để quay về thư mục cha. | Nielsen #6: Recognition | NA |  |
| IA-03-06 | Navigation | Tính năng kéo thả thay đổi thứ tự (Reorder) hiển thị trực quan (dòng bị kéo mờ opacity-50) và các nút thao tác khác tạm thời bị vô hiệu hóa. | Norman: Feedback | NA | Không có drag-and-drop/reorder feature trên màn hình Check-in. |
| IA-03-07 | Navigation | Các tab chuyển đổi nhanh hoạt động độc lập và tải đúng dữ liệu tương ứng. | Nielsen #7: Flexibility | Pass | Chuyển giữa "Checked In" và "Scan Logs" sub-tab — mỗi tab load đúng nội dung (khác nhau: bảng user vs bảng scan log). |
| IA-03-08 | Navigation | Không có liên kết nào bị hỏng (Broken links / 404 error) trên toàn giao diện. | Nielsen #4: Consistency | Pass | Kiểm tra 11 links trên trang — tất cả đều là valid internal paths. |
| IA-03-09 | Navigation | Nút "Cuộn lên đầu trang" (Back to top) hiển thị khi người dùng cuộn xuống sâu (nếu có). | Nielsen #7: Flexibility | NA | Màn hình không đủ dài để cần scroll-to-top; không có nút này. |
| IA-03-10 | Navigation | Thanh bên sidebar có thể thu gọn/mở rộng mượt mà và không che khuất nội dung chính. | Nielsen #3: User Control | Pass | Sidebar collapse hoạt động mượt mà — thu gọn xuống icon-only, content area mở rộng tương ứng. |
| IA-03-11 | Navigation | Đường dẫn URL trên thanh địa chỉ thay đổi tương ứng khi chuyển đổi qua lại giữa các tab hoặc bộ lọc. | Nielsen #4: Consistency | Fail | URL giữ nguyên ?tab=checkin khi switch giữa sub-tab "Checked In" và "Scan Logs" — không cập nhật thêm parameter cho sub-tab. Deep link đến sub-tab cụ thể là không thể. Ảnh: screenshots/A5-bug-IA-03-11.png |
| IA-03-12 | Navigation | Giao diện kéo thả (Reorder) hiển thị biểu tượng tay cầm (drag handle) rõ ràng để gợi ý khả năng tương tác. | Norman: Signifiers | NA | Không có drag-and-drop feature trên màn hình Check-in. |
| **IA-04** | **Feedback** | **IA-04: Feedback & State (Toasts, Badges, Confirmations, Progress Bars, Status Colors)** | | | |
| IA-04-01 | Feedback | Thông báo nổi (Toasts) xuất hiện ngay sau khi thực hiện hành động và tự động tắt sau 3-5s. | Norman: Feedback | Fail | Click "Export" với bảng rỗng ("No results") không kích hoạt bất kỳ toast hay feedback nào.|
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
| IA-04-14 | Feedback | Các nút secondary actions phải được vô hiệu hóa (disabled + đổi con trỏ) khi không có gì để thực hiện, hoặc phải hiển thị phản hồi rõ ràng (toast/thông báo) nếu vẫn cho phép bấm mà không có tác dụng gì | Norman: Feedback + Signifiers | Fail | Nút "Export" khi bảng rỗng: vẫn enabled và clickable, nhưng không có response nào (không toast, không file download, không API call) — vi phạm nghiêm trọng.|

---

## Screen 3: Dashboard

| IA | Item # | Checklist Item | Pass/Fail | Notes (lý do Fail) | Screenshot ref |
|---|---|---|---|---|---|
| | | | | | |
| **IA-01** | **General UI** | **General UI Standards** | | | | |
| IA-01-01 | General UI | Hệ thống lưới và khoảng cách (Grid & Spacing) căn lề nhất quán trên toàn màn hình. | Nielsen #4 | Pass | Sidebar, header, and main use consistent grid. Nav items use `px-3 py-2.5`. KPI cards are evenly spaced. No misalignment observed. | |
| IA-01-02 | General UI | Font chữ (typography) nhất quán về kích thước, độ dày (bold/regular) và phân cấp tiêu đề. | Nielsen #4 | Pass | Single font (`ui-sans-serif`). H1 uses `text-4xl font-black`. Clear hierarchy: H1 > body text > labels. Consistent throughout. | |
| IA-01-03 | General UI | Màu sắc của các nút hành động (Primary, Secondary) và trạng thái nhất quán. | Norman: Signifiers | Pass | Sidebar uses dark bg `rgb(24,24,27)` with cyan active highlight `#1bc2f5`. No action buttons on landing page — consistent with system-wide pattern. | |
| IA-01-04 | General UI | Đa ngôn ngữ (EN/VI) hoạt động đầy đủ, không bị dịch thiếu hoặc chồng lấp chữ. | Nielsen #4 | Pass |
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
| IA-03-05 | Navigation | Breadcrumbs hiển thị đúng phân cấp thư mục và có thể click để quay về thư mục cha. | Nielsen #6 | NA | |
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
| IA-04-04 | Feedback | Huy hiệu (Badges) hiển thị chính xác số lượng thông báo. | Nielsen #1 | NA |  |
| IA-04-05 | Feedback | Thanh tiến trình (Progress bar) hoặc vòng xoay tải (Spinner) xuất hiện khi hệ thống xử lý. | Nielsen #1 | NA | No async operations triggered during this run. Cannot verify spinner behavior. | |
| IA-04-06 | Feedback | Trạng thái hiển thị màu sắc tương thích với ngữ nghĩa (APPROVED xanh lá, REJECTED đỏ). | Nielsen #2 | NA | No status badges on this page. KPI cards show plain numeric values. | |
| IA-04-07 | Feedback | Chấm đỏ thông báo (Notification dot) hiển thị động ngay khi có thay đổi trạng thái đăng ký. | Nielsen #1 | NA |  |
| IA-04-08 | Feedback | Hộp thoại chi tiết ảnh (Lightbox) mở rộng mượt mà khi click vào ảnh đính kèm. | Nielsen #7 | NA | No clickable image attachments on this page. | |
| IA-04-09 | Feedback | Cập nhật dữ liệu thời gian thực (Real-time update) mà không cần người dùng reload trang. | Norman | NA | Requires two simultaneous sessions to verify. Manual testing needed. | |
| IA-04-10 | Feedback | Hiển thị thông báo rõ ràng khi mất kết nối mạng Internet. | Nielsen #1 | NA | Cannot simulate network disconnect in this environment. Manual testing needed. | |
| IA-04-11 | Feedback | Hệ thống vô hiệu hóa nút gửi hoặc ngăn chặn gửi dữ liệu trùng lặp khi người dùng click đúp. | Nielsen #5 | NA | No Submit buttons on this page. | |
| IA-04-12 | Feedback | Mã QR/Barcode trên vé hiển thị rõ nét (không bị mờ). | Nielsen #1 | NA | No QR codes on this page. | |
| IA-04-13 | Feedback | Ô nhập liệu (text box) hiển thị hiệu ứng viền/nổi bật trực quan (focus state). | Norman | NA | No text inputs on the Dashboard landing page. | |
| IA-04-14 | Feedback | Các nút secondary actions phải được vô hiệu hóa (disabled) khi không có gì để thực hiện. | Norman | NA | No secondary action buttons on this page. | |


---

## Tổng kết toàn bộ

| Screen | Tổng item | Pass | Fail | N/A | % Pass (Đã test) | % Pass (Tổng) |
|---|---|---|---|---|---|---|
| Screen A4: Participants & Reviews | 50 | 24 | 6 | 20 | 80.0% (24/30) | 48.0% (24/50) |
| Screen A5: Check-in tab | 50 | 21 | 4 | 25 | 84.0% (21/25) | 42.0% (21/50) |
| Screen 3: Admin Dashboard (KPIs) | 50 | 11 | 2 | 37 | 84.6% (11/13) | 22.0% (11/50) |
| **TOTAL** | **150** | **56** | **12** | **82** | **82.4% (56/68)** | **37.3% (56/150)** |
