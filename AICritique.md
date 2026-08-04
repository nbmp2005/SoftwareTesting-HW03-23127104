# AI Critique (200–300 words, Mandatory)

> Viết 1 đoạn văn (không phải bullet list) 200-300 từ, trả lời:
> - AI đã sai/thiếu/lệch (biased) ở đâu?
> - Vì sao AI không phát hiện ra vấn đề đó?
> - Bài học gì bạn rút ra về việc collaborate với AI?

---

[Bắt đầu viết đoạn văn tại đây. Gợi ý cấu trúc 3 phần:

**Phần 1 (chỗ AI sai/thiếu):** Ví dụ AI khi được yêu cầu generate GUI checklist ban đầu đã tạo ra
các item mang tính tổng quát (generic) như "buttons should be clickable" hoặc bỏ qua hoàn toàn
các đặc thù nghiệp vụ của EMS như quy tắc duyệt multi-role trong A4, hay 4 trạng thái quét
check-in trong A5. AI cũng có xu hướng không đề cập tới accessibility, dark mode, hay i18n sâu
trừ khi được prompt trực tiếp.

**Phần 2 (vì sao AI không phát hiện ra):** Vì AI không có quyền truy cập trực tiếp vào EMS, nó
chỉ dựa vào phần mô tả bạn cung cấp trong prompt; nếu prompt không đủ chi tiết về logic
nghiệp vụ, AI sẽ trả lời ở mức general heuristic thay vì domain-specific. Ngoài ra AI thiên về
pattern phổ biến trong training data (web app "điển hình"), nên bỏ sót các ràng buộc rất đặc thù
chỉ có trong EMS.

**Phần 3 (bài học):** Bài học rút ra là AI hoạt động tốt nhất như một "bộ khung tăng tốc" (scaffold)
chứ không phải nguồn sự thật cuối cùng; người dùng vẫn phải hiểu sâu hệ thống thực tế, cung
cấp context cụ thể, và luôn review/bổ sung bằng kiến thức miền (domain knowledge) của mình...]

*(Đảm bảo tổng số từ nằm trong khoảng 200-300 từ trước khi nộp)*