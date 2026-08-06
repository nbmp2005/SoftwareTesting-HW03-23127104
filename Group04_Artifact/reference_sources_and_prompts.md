# Reference Sources & Prompts - Group Deliverable

## 1. Nguồn Tài Liệu Tham Khảo (Reference Sources)

Nhóm đã nghiên cứu và xây dựng bộ checklist GUI dựa trên các tài liệu chính thống sau:
*   **Nielsen's 10 Usability Heuristics for User Interface Design**: [Jakob Nielsen - NN/g](https://www.nngroup.com/articles/ten-usability-heuristics/)
*   **Norman's 6 Design Principles**: Trích từ nguồn cuốn sách *The Design of Everyday Things* (Donald Norman), và được nêu vắn tắt dưới dạng 6 tiêu chí bao gồm: Visibility, Feedback, Constraints, Mapping, Consistency, Affordances.
*   **Shneiderman's Eight Golden Rules of Interface Design**: [Ben Shneiderman](https://www.cs.umd.edu/users/ben/goldenrules.html)
*   **Tài liệu chuẩn mực WCAG 2.1**: Hướng dẫn tiếp cận nội dung web về độ tương phản.

---

## 2. Nhật Ký Prompts Sử Dụng Cho AI (AI Prompts Log)

Dưới đây là các câu lệnh (prompts) được nhóm thiết kế để hướng dẫn AI hỗ trợ tạo lập checklist:

### Prompt 1: Khởi tạo danh sách checklist ban đầu dựa trên Heuristics
*   **Công cụ:** Gemini 3.6 Flash (Antigravity)
*   **Thời gian:** 21:36 25/07/2026
*   **Nội dung Prompt:**
    ```text
    Bạn là một kỹ sư kiểm thử phần mềm chuyên nghiệp. Hãy đóng vai trò là trợ lý thiết kế danh sách checklist kiểm thử GUI cho một ứng dụng web Quản lý Sự kiện (Event Management System - EMS).
    Hãy tạo lập một bộ checklist gồm ít nhất 30 mục kiểm tra, phân bố đều vào 4 khía cạnh giao diện sau:
    1. IA-01: General UI standards (Bố cục, căn lề, font chữ, đa ngôn ngữ, trạng thái rỗng/đang tải).
    2. IA-02: Forms (Nhãn, validation lỗi, trường bắt buộc, upload ảnh, rich text).
    3. IA-03: Navigation (Menu, breadcrumbs, sidebar, tabs, reorder kéo thả, nút back).
    4. IA-04: Feedback & State (Toasts, badges, hộp thoại xác nhận, progress bars, màu trạng thái).
    
    Yêu cầu: Mỗi mục kiểm tra phải ánh xạ rõ ràng tới một trong các nguyên tắc Usability nổi tiếng (10 Heuristics của Nielsen, 6 nguyên tắc của Norman, hoặc 8 quy tắc vàng của Shneiderman). Xuất kết quả dạng bảng Markdown có các cột: ID, Khía Cạnh, Mục Kiểm Tra, Ánh Xạ Heuristic.
    ```
*   **Kết quả prompt:**
    ```text
    tôi đã tạo xong shared_gui_checklist.md: Khung checklist GUI đã được điền sẵn hơn 40 mục kiểm tra phân chia đều vào 4 khía cạnh giao diện (IA-01 đến IA-04), kèm cột Pass/Fail cho từng màn hình 1 đến 3 và ánh xạ chi tiết sang Heuristics của Nielsen/Norman/Shneiderman.
    ```

### Prompt 2: Tinh chỉnh và bổ sung các kịch bản kiểm thử đặc thù của EMS
*   **Công cụ:** Gemini 3.6 Flash (Antigravity)
*   **Thời gian:** 21:51 25/07/2026
*   **Nội dung Prompt:**
    ```text
    Từ bộ checklist GUI đã tạo ở trên, hãy bổ sung các kịch bản kiểm thử nâng cao và thực tế cho hệ thống EMS, cụ thể:
    - Cách thức kiểm duyệt ảnh tải lên với tỷ lệ khung hình cố định (Thumbnail 4:3 và Banner 24:9).
    - Tính năng kéo thả Reorder để sắp xếp thứ tự danh mục hoặc context học thuật (Academic Contexts).
    - Trạng thái phản hồi trực quan khi người dùng nằm trong danh sách chờ (Waitlist) hoặc đăng ký thành công lấy vé QR code.
    ```
*   **Kết quả prompt:**
    ```text
    tôi đã bổ sung và tinh chỉnh lại shared_gui_checklist.md cho hệ thống EMS:
    - Thêm các mục kiểm thử nâng cao về tỷ lệ ảnh (Aspect Ratio Validation), tính năng kéo thả Reorder, trạng thái Waitlist và QR code.
    ```

---

## 3. Giải Trình Bổ Sung Đóng Góp Từ Con Người (Human Review Analysis)

AI đã tạo ra khung checklist rất tốt, nhóm đã phát hiện ra AI thường bỏ sót các điểm kiểm thử có tính chất **ngữ cảnh thực tế cao** hoặc **quy trình nghiệp vụ đặc thù của EMS**. Dưới đây là phân tích chi tiết:

1.  **Lỗi kiểm tra tỷ lệ ảnh (Aspect Ratio Validation):**
    *   *AI bỏ sót vì:* AI thường chỉ đưa ra quy tắc chung như "kiểm tra ảnh tải lên thành công".
    *   *Con người bổ sung:* Thêm mục kiểm tra tính năng hiển thị ảnh Thumbnail (4:3) và Banner (24:9) không bị méo lệch tỉ lệ trên các kích thước màn hình khác nhau.
2.  **Trạng thái kéo thả Reorder (Drag & Drop states):**
    *   *AI bỏ sót vì:* AI không hiểu sâu về cách thức tương tác kéo thả cần có phản hồi thị giác (visual feedback) thế nào.
    *   *Con người bổ sung:* Thêm chi tiết khi kéo thả, các nút thao tác khác tạm thời bị vô hiệu hóa để tránh xung đột hành động.
3.  **Tích hợp vé Barcode/QR Code:**
    *   *AI bỏ sót vì:* Đây là tính năng nghiệp vụ đặc thù của kịch bản B (Participant ticket).
    *   *Con người bổ sung:* Thêm mục kiểm tra chất lượng hiển thị mã QR/Barcode (không bị mờ, quét được bằng camera điện thoại thông thường) và trạng thái hiển thị vé thay đổi tương ứng khi được phê duyệt/hủy.
