# Shared GUI Checklist - Group Deliverable

## Bảng Checklist GUI Tổng Hợp

| ID | Khía Cạnh | Mục Kiểm Tra (Checklist Item Description) | Ánh Xạ Heuristics / Nguyên Tắc | Screen 1 (Pass/Fail/NA) | Screen 2 (Pass/Fail/NA) | Screen 3 (Pass/Fail/NA) | Ghi Chú Lỗi (Notes) |
|---|---|---|---|---|---|---|---|
| **IA-01** | **General UI** | **IA-01: General UI Standards (Layout, Typography, Color, Consistency, i18n)** | | | | | |
| IA-01-01 | General UI | Hệ thống lưới và khoảng cách (Grid & Spacing) căn lề nhất quán trên toàn màn hình. | Nielsen #4: Consistency | | | | |
| IA-01-02 | General UI | Font chữ (typography) nhất quán về kích thước, độ dày (bold/regular) và phân cấp tiêu đề. | Nielsen #4: Consistency | | | | |
| IA-01-03 | General UI | Màu sắc của các nút hành động (Primary, Secondary) và trạng thái nhất quán. | Norman: Signifiers | | | | |
| IA-01-04 | General UI | Đa ngôn ngữ (EN/VI) hoạt động đầy đủ, không bị dịch thiếu hoặc chồng lấp chữ. | Nielsen #4: Consistency | | | | |
| IA-01-05 | General UI | Trạng thái rỗng (Empty state) được hiển thị rõ ràng khi không có sự kiện/dữ liệu nào. | Nielsen #1: Visibility | | | | |
| IA-01-06 | General UI | Trạng thái đang tải (Loading state/skeleton) hiển thị khi kéo dữ liệu chậm. | Nielsen #1: Visibility | | | | |
| IA-01-07 | General UI | Trang web tương thích tốt và tự động co giãn (Responsive) trên màn hình. | Nielsen #4: Consistency | | | | |
| IA-01-08 | General UI | Các hình ảnh (Thumbnail/Banner) không bị méo tỉ lệ hiển thị (tỷ lệ 4:3 và 24:9) trên các kích thước màn hình khác nhau. | Shneiderman: Aesthetics | | | | |
| IA-01-09 | General UI | Các icon được căn chỉnh đúng tâm so với nhãn text bên cạnh. | Shneiderman: Aesthetics | | | | |
| IA-01-10 | General UI | Độ tương phản màu sắc giữa văn bản và nền đủ rõ ràng (Accessibility WCAG). | Nielsen #4: Consistency | | | | |
| IA-01-11 | General UI | Các liên kết ngoài (External links) mở ở tab mới, liên kết nội bộ (Internal links) mở ở tab hiện tại. | Nielsen #3: User Control | | | | |
| IA-01-12 | General UI | Ảnh Thumbnail (4:3) và Banner (24:9) không bị cắt xén mất nội dung quan trọng. | Nielsen #4: Consistency | | | | |
| **IA-02** | **Forms** | **IA-02: Forms (Labels, Validation, Errors, Required Fields, Rich Text)** | | | | | |
| IA-02-01 | Forms | Các trường bắt buộc nhập (Required fields) được đánh dấu ký hiệu trực quan (ví dụ dấu `*`). | Norman: Constraints | | | | |
| IA-02-02 | Forms | Nhãn (Labels) của trường nhập liệu luôn hiển thị rõ ràng và đi sát với ô nhập liệu. | Nielsen #6: Recognition | | | | |
| IA-02-03 | Forms | Validation thời gian thực báo lỗi đỏ trực quan ngay dưới trường nhập liệu bị lỗi. | Nielsen #5: Error Prev. | | | | |
| IA-02-04 | Forms | Thông báo lỗi cụ thể, hướng dẫn cách khắc phục thay vì báo lỗi chung chung. | Nielsen #10: Help & Error | | | | |
| IA-02-05 | Forms | Định dạng tải lên (Upload file/image) kiểm tra đúng định dạng và dung lượng tối đa. | Norman: Constraints | | | | |
| IA-02-06 | Forms | Trình soạn thảo Rich Text hiển thị đầy đủ thanh công cụ và hoạt động mượt mà. | Nielsen #7: Flexibility | | | | |
| IA-02-07 | Forms | Người dùng có thể nhấn `Tab` để di chuyển tuần tự qua các ô nhập liệu trong form. | Nielsen #7: Flexibility | | | | |
| IA-02-08 | Forms | Các nút Submit/Save bị vô hiệu hóa (disabled) khi form chưa điền đủ thông tin hợp lệ. | Nielsen #5: Error Prev. | | | | |
| IA-02-09 | Forms | Định dạng ngày giờ hiển thị theo chuẩn cục bộ dễ đọc đối với người dùng Việt Nam. | Nielsen #2: Match System | | | | |
| IA-02-10 | Forms | Nút xóa nhanh (clear button) hoặc reset form hoạt động chính xác. | Nielsen #3: User Control | | | | |
| IA-02-11 | Forms | Trình duyệt hỗ trợ tính năng tự động điền (autofill) cho các trường thông tin cơ bản. | Nielsen #7: Flexibility | | | | |
| IA-02-12 | Forms | Ô nhập mật khẩu hỗ trợ tính năng toggle ẩn/hiện mật khẩu trực quan bằng biểu tượng con mắt. | Nielsen #7: Flexibility | | | | |
| **IA-03** | **Navigation** | **IA-03: Navigation (Menus, Breadcrumbs, Sidebar, Tabs, Back actions, Deep links)** | | | | | |
| IA-03-01 | Navigation | Menu điều hướng chính luôn cố định hoặc dễ dàng truy cập ở đầu trang/thanh bên. | Nielsen #6: Recognition | | | | |
| IA-03-02 | Navigation | Trạng thái hiện tại của trang (Active state) được làm nổi bật trên menu điều hướng. | Nielsen #1: Visibility | | | | |
| IA-03-03 | Navigation | Nút quay lại (Back/Return action) đưa người dùng về đúng trang trước đó, không mất trạng thái. | Nielsen #3: User Control | | | | |
| IA-03-04 | Navigation | Liên kết sâu (Deep links) dẫn trực tiếp đến trang chi tiết sự kiện mà không bị lỗi 404. | Nielsen #4: Consistency | | | | |
| IA-03-05 | Navigation | Breadcrumbs hiển thị đúng phân cấp thư mục và có thể click để quay về thư mục cha. | Nielsen #6: Recognition | | | | |
| IA-03-06 | Navigation | Tính năng kéo thả thay đổi thứ tự (Reorder) hiển thị trực quan (dòng bị kéo mờ opacity-50) và các nút thao tác khác tạm thời bị vô hiệu hóa. | Norman: Feedback | | | | |
| IA-03-07 | Navigation | Các tab chuyển đổi nhanh hoạt động độc lập và tải đúng dữ liệu tương ứng. | Nielsen #7: Flexibility | | | | |
| IA-03-08 | Navigation | Không có liên kết nào bị hỏng (Broken links / 404 error) trên toàn giao diện. | Nielsen #4: Consistency | | | | |
| IA-03-09 | Navigation | Nút "Cuộn lên đầu trang" (Back to top) hiển thị khi người dùng cuộn xuống sâu (nếu có). | Nielsen #7: Flexibility | | | | |
| IA-03-10 | Navigation | Thanh bên sidebar có thể thu gọn/mở rộng mượt mà và không che khuất nội dung chính. | Nielsen #3: User Control | | | | |
| IA-03-11 | Navigation | Đường dẫn URL trên thanh địa chỉ thay đổi tương ứng khi chuyển đổi qua lại giữa các tab hoặc bộ lọc. | Nielsen #4: Consistency | | | | |
| IA-03-12 | Navigation | Giao diện kéo thả (Reorder) hiển thị biểu tượng tay cầm (drag handle) rõ ràng để gợi ý khả năng tương tác. | Norman: Signifiers | | | | |
| **IA-04** | **Feedback** | **IA-04: Feedback & State (Toasts, Badges, Confirmations, Progress Bars, Status Colors)** | | | | | |
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
| IA-04-13 | Feedback | Ô nhập liệu (text box) hiển thị hiệu ứng viền/nổi bật trực quan (focus state) khi nhấp chuột vào để người dùng nhận biết rõ ràng đang thao tác/nhập liệu. | Norman: Feedback | | | | |
| IA-04-14 | Feedback | Các nút secondary actions phải được vô hiệu hóa (disabled + đổi con trỏ) khi không có gì để thực hiện, hoặc phải hiển thị phản hồi rõ ràng (toast/thông báo) nếu vẫn cho phép bấm mà không có tác dụng gì | Norman: Feedback + Signifiers | | | | |
