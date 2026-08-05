# Task 3 — Cross-Browser / Cross-Platform Compatibility Matrix

> Yêu cầu: mỗi screen phải phủ ít nhất 1 lần MỖI OS (3), MỖI browser (5), MỖI device class (3).
> Không cần đủ 45 combo — chỉ cần đảm bảo mỗi chiều xuất hiện ít nhất 1 lần cho MỖI screen.
> Mọi screenshot phải overlay: `MSSV@...edu.vn` + tên browser/OS/device + URL EMS.
> Công cụ dùng: BrowserStack (Live, real device cloud) — qua BrowserStack MCP Server
> Scenario: A — Theo dõi và vận hành sự kiện (Dashboard / A4 / A5)

---

## Screen 1: Admin Dashboard (KPIs)

| # | OS | Browser | Device class | Pass/Fail | Ghi chú lỗi (nếu Fail) | Screenshot ref |
|---|---|---|---|---|---|---|
| 1 | Windows | Chrome | Desktop | | | screenshots/cp_dashboard_win_chrome_desktop.png |
| 2 | Windows | Firefox | Desktop | | | screenshots/cp_dashboard_win_firefox_desktop.png |
| 3 | macOS | Safari | Desktop | | | screenshots/cp_dashboard_macos_safari_desktop.png |
| 4 | macOS | Edge | Desktop | | | screenshots/cp_dashboard_macos_edge_desktop.png |
| 5 | Android | Chrome | Phone | | | screenshots/cp_dashboard_android_chrome_phone.png |
| 6 | Android | Samsung Internet | Tablet | | | screenshots/cp_dashboard_android_samsunginternet_tablet.png |
| 7 | iOS | Safari | Phone | | | screenshots/cp_dashboard_ios_safari_phone.png |

> Kiểm tra: đã phủ đủ 3 OS (Windows/macOS/Android/iOS) ✅ | đủ 5 browser (Chrome/Firefox/Safari/Edge/Samsung Internet) ✅ | đủ 3 device class (Desktop/Tablet/Phone) ✅

**Tổng kết Screen 1:** [x] Pass / [y] Fail

---

## Screen 2: A4 — Participants & Reviews Approval
(gồm 3 tab con: Registrants | Review Lecturers | Review Students — ưu tiên test trên tab Review Students vì có nhiều nút hành động nhất)

| # | OS | Browser | Device class | Pass/Fail | Ghi chú lỗi (nếu Fail) | Screenshot ref |
|---|---|---|---|---|---|---|
| 1 | Windows | Chrome | Desktop | | | screenshots/cp_A4_win_chrome_desktop.png |
| 2 | Windows | Firefox | Desktop | | | screenshots/cp_A4_win_firefox_desktop.png |
| 3 | macOS | Safari | Desktop | | | screenshots/cp_A4_macos_safari_desktop.png |
| 4 | macOS | Edge | Desktop | | | screenshots/cp_A4_macos_edge_desktop.png |
| 5 | Android | Chrome | Phone | | | screenshots/cp_A4_android_chrome_phone.png |
| 6 | Android | Samsung Internet | Tablet | | | screenshots/cp_A4_android_samsunginternet_tablet.png |
| 7 | iOS | Safari | Phone | | | screenshots/cp_A4_ios_safari_phone.png |

> Kiểm tra: đã phủ đủ 3 OS ✅ | đủ 5 browser ✅ | đủ 3 device class ✅

**Tổng kết Screen 2:** [x] Pass / [y] Fail

---

## Screen 3: A5 — Check-in Tab

| # | OS | Browser | Device class | Pass/Fail | Ghi chú lỗi (nếu Fail) | Screenshot ref |
|---|---|---|---|---|---|---|
| 1 | Windows | Chrome | Desktop | | | screenshots/cp_A5_win_chrome_desktop.png |
| 2 | Windows | Firefox | Desktop | | | screenshots/cp_A5_win_firefox_desktop.png |
| 3 | macOS | Safari | Desktop | | | screenshots/cp_A5_macos_safari_desktop.png |
| 4 | macOS | Edge | Desktop | | | screenshots/cp_A5_macos_edge_desktop.png |
| 5 | Android | Chrome | Phone | | | screenshots/cp_A5_android_chrome_phone.png |
| 6 | Android | Samsung Internet | Tablet | | | screenshots/cp_A5_android_samsunginternet_tablet.png |
| 7 | iOS | Safari | Phone | | | screenshots/cp_A5_ios_safari_phone.png |

> Kiểm tra: đã phủ đủ 3 OS ✅ | đủ 5 browser ✅ | đủ 3 device class ✅
> Lưu ý riêng cho A5: đây là màn hình rất có khả năng dùng thật trên điện thoại tại
> sự kiện — ưu tiên quan sát kỹ khung quét mã và log real-time trên các cell Phone/Tablet.

**Tổng kết Screen 3:** [x] Pass / [y] Fail

---

## Tổng kết toàn bộ Compatibility Testing

| Screen | Số cell đã test | Pass | Fail | OS đủ? | Browser đủ? | Device đủ? |
|---|---|---|---|---|---|---|
| Dashboard | 7 | | | | | |
| A4 - Participants & Reviews | 7 | | | | | |
| A5 - Check-in | 7 | | | | | |
| **TOTAL** | 21 | | | | | |

## Chi tiết các lỗi Fail (rendering/layout)

| Screen | OS/Browser/Device | Loại lỗi (overflow/overlap/broken layout/unreadable text/non-responsive) | Mô tả chi tiết |
|---|---|---|---|
| | | | |