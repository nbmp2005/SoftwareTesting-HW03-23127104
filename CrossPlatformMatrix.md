# Task 3 — Cross-Browser / Cross-Platform Compatibility Matrix
---

## Screen 1: Admin Dashboard (KPIs)

| # | OS | Browser | Device class | Pass/Fail | Ghi chú lỗi (nếu Fail) | Screenshot ref |
|---|---|---|---|---|---|---|
| 1 | Windows | Chrome | Desktop | **PASS** | Giao diện chuẩn, hiển thị đầy đủ KPI cards & sidebar navigation. | [cp_dashboard_win_chrome_desktop.png](images/cross_platform/cp_dashboard_windows_chrome_desktop.png) |
| 2 | Windows | Firefox | Desktop | **PASS** | Giao diện chuẩn, các thẻ thông số căn chỉnh đẹp. | [cp_dashboard_win_firefox_desktop.png](images/cross_platform/cp_dashboard_windows_firefox_desktop.png) |
| 3 | macOS | Edge | Desktop | **PASS** | Giao diện chuẩn Chromium trên macOS. | [cp_dashboard_macos_edge_desktop.png](images/cross_platform/cp_dashboard_macos_edge_desktop.png) |
| 4 | Android | Samsung Internet | Tablet | **PASS** | Trên Tablet (768px), sidebar + KPI cards vừa đủ không bị cuộn ngang. | [cp_dashboard_android_samsunginternet_tablet.png](images/cross_platform/cp_dashboard_android_samsunginternet_tablet.png) |
| 5 | iOS | Safari | Phone | **FAIL** | **Non-responsive / Layout Broken**: Sidebar không tự thu gọn trên iOS Safari Phone (390px), gây tràn lề ngang severe. | [cp_dashboard_ios_safari_phone.png](images/cross_platform/cp_dashboard_ios_safari_phone.png) |


**Tổng kết Screen 1:** 4 Pass / 1 Fail

---

## Screen 2: A4 — Participants & Reviews Approval
*(Tab Review Students — URL: `/dashboard/admin/events/views?id=141&tab=student-review`)*

| # | OS | Browser | Device class | Pass/Fail | Ghi chú lỗi (nếu Fail) | Screenshot ref |
|---|---|---|---|---|---|---|
| 1 | Windows | Chrome | Desktop | **PASS** | Đầy đủ sub-tabs, search bar, các nút hành động (Reject All, Approve All, Cancel All, Apply) và bảng danh sách. | [cp_A4_win_chrome_desktop.png](images/cross_platform/cp_A4_win_chrome_desktop.png) |
| 2 | Windows | Firefox | Desktop | **PASS** | Căn chỉnh chuẩn, bảng Review Students hiển thị sắc nét. | [cp_A4_win_firefox_desktop.png](images/cross_platform/cp_A4_win_firefox_desktop.png) |
| 3 | macOS | Edge | Desktop | **PASS** | Đầy đủ tính năng và nút hành động. | [cp_A4_macos_edge_desktop.png](images/cross_platform/cp_A4_macos_edge_desktop.png) |
| 4 | Android | Samsung Internet | Tablet | **FAIL** | **Horizontal Overflow**: Bảng danh sách 5 cột (STUDENT, ROLE, ACTION...) + hàng nút bấm vượt quá bề rộng 768px, xuất hiện thanh cuộn ngang toàn trang. | [cp_A4_android_samsunginternet_tablet.png](images/cross_platform/cp_A4_android_samsunginternet_tablet.png) |
| 5 | iOS | Safari | Phone | **FAIL** | **Layout Broken**: Sidebar cố định không ẩn làm cụm Review Students bị đẩy tràn lề phải. | [cp_A4_ios_safari_phone.png](images/cross_platform/cp_A4_ios_safari_phone.png) |


**Tổng kết Screen 2:** 3 Pass / 2 Fail

---

## Screen 3: A5 — Check-in Tab
*(URL: `/dashboard/admin/events/views?id=141&tab=checkin`)*

| # | OS | Browser | Device class | Pass/Fail | Ghi chú lỗi (nếu Fail) | Screenshot ref |
|---|---|---|---|---|---|---|
| 1 | Windows | Chrome | Desktop | **PASS** | Đầy đủ 6 KPI cards, khung nhập mã Barcode, bộ lọc Checked In/Scan Logs và bảng dữ liệu. | [cp_A5_win_chrome_desktop.png](images/cross_platform/cp_A5_win_chrome_desktop.png) |
| 2 | Windows | Firefox | Desktop | **PASS** | Giao diện chuẩn, khung Barcode & thẻ KPI sắp xếp đúng lưới. | [cp_A5_win_firefox_desktop.png](images/cross_platform/cp_A5_win_firefox_desktop.png) |
| 3 | macOS | Edge | Desktop | **PASS** | Giao diện chuẩn trên Edge macOS. | [cp_A5_macos_edge_desktop.png](images/cross_platform/cp_A5_macos_edge_desktop.png) |
| 4 | Android | Samsung Internet | Tablet | **FAIL** | **Grid Overflow**: Hàng 6 thẻ KPI xếp ngang không wrap (xuống dòng) trên màn hình 768px, làm vỡ khung Check-in. | [cp_A5_android_samsunginternet_tablet.png](images/cross_platform/cp_A5_android_samsunginternet_tablet.png) |
| 5 | iOS | Safari | Phone | **FAIL** | **Unusable on Mobile**: Sidebar làm lệch toàn bộ ô quét Barcode & bảng Scan Logs off-screen trên iPhone. | [cp_A5_ios_safari_phone.png](images/cross_platform/cp_A5_ios_safari_phone.png) |


**Tổng kết Screen 3:** 3 Pass / 2 Fail

---

## Tổng kết toàn bộ Compatibility Testing

| Screen | Số cell đã test | Pass | Fail | OS đủ? | Browser đủ? | Device đủ? |
|---|---|---|---|---|---|---|
| Dashboard | 5 | 4 | 1 | 4 OS | 5 Browsers | 3 Devices |
| A4 - Participants & Reviews | 5 | 3 | 2 | 4 OS | 5 Browsers | 3 Devices |
| A5 - Check-in | 5 | 3 | 2 | 4 OS | 5 Browsers | 3 Devices |
| **TOTAL** | **15** | **10** | **5** | 4 OS | 5 Browsers | 3 Devices |

---

## Chi tiết các lỗi Fail (rendering/layout)

| Screen | OS/Browser/Device | Loại lỗi | Mô tả chi tiết |
|---|---|---|---|
| Dashboard | iOS / Safari / Phone (390px) | Non-responsive / Layout Broken | Tương tự trên WebKit iOS, tiêu đề Dashboard & các thẻ KPI bị tràn khỏi khung nhìn màn hình. |
| A4 - Review Students | Android / Samsung Internet / Tablet (768px) | Horizontal Overflow | Bảng dữ liệu 5 cột không có cuộn nội bộ (`overflow-x: auto` trên table wrapper) làm tràn lề toàn màn hình Tablet. |
| A4 - Review Students | iOS / Safari / Phone (390px) | Action Buttons Hidden / Broken Layout | Giao diện bị đẩy lệch khỏi lề phải, nút duyệt và ô tìm kiếm bị giấu đằng sau viền màn hình. |
| A5 - Check-in | Android / Samsung Internet / Tablet (768px) | Grid Overflow | Grid 6 thẻ KPI (`Total Check-ins`, `Lecturer`, `Student`, `Total Scans`, `Successful`, `Failed`) cố định không vừa màn hình Tablet 768px, làm khung Barcode bị đẩy xô lệch. |
| A5 - Check-in | iOS / Safari / Phone (390px) | Unusable UI / Element Overlap | Không thể sử dụng tính năng Check-in sự kiện trên Mobile Safari do các yếu tố bị tràn viền và che khuất. |