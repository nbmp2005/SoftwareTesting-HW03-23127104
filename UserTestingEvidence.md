# Task 2 — User Testing with 5 Real Users → Usability Report

---

## PHASE 1 — Design & Prepare

### 1.1. Task Scenario

```
Bối cảnh trao cho người tham gia:
"Bạn là nhân viên phụ trách vận hành một sự kiện của trường sắp diễn ra. Có một số
người vừa đăng ký tham dự đang chờ được duyệt, và sự kiện cũng đang có người đến
check-in trực tiếp tại cửa. Hãy dùng hệ thống EMS Admin để xử lý công việc hôm nay
của bạn."

Nhiệm vụ cụ thể:
"Hãy vào xử lý những người đang chờ duyệt đăng ký — chấp nhận những người hợp lệ.
Cuối cùng, hãy giả sử có một người mới vừa đến sự kiện, hãy xử lý check-in cho họ
và xác nhận là hệ thống đã ghi nhận thành công."
```

### 1.2. Metrics sẽ đo

| Metric | Cách đo |
|---|---|
| Task success | Completed / Partial / Failed |
| Time on task | Bấm giờ từ lúc bắt đầu đến lúc hoàn thành/từ bỏ |
| Error / hesitation count | Đếm số lần click sai, quay lại, dừng lại lâu (>5s không thao tác) |
| SUS score (hoặc UEQ-S) | Thang điểm chuẩn sau khi hoàn thành task |

### 1.3. Probe Questions (hỏi cuối mỗi session, sau SUS/UEQ-S)

| # | Khía cạnh | Câu hỏi |
|---|---|---|
| Q1 | Clarity | Điều gì (nếu có) khiến bạn không chắc mình đang thao tác đúng? |
| Q2 | Error recovery | Nếu bạn bấm nhầm hoặc vào sai chỗ, bạn có biết cách quay lại không? Vì sao? |
| Q3 | Speed | Bạn thấy tốc độ hoàn thành task này nhanh/chậm hơn bạn mong đợi thế nào? |
| Q4 | Trust | Bạn có tin chắc hệ thống đã ghi nhận đúng hành động (duyệt / check-in) của mình không? Vì sao? |

### 1.4. Pilot Session (1 người, trước 5 session chính thức)

| Nội dung | Chi tiết |
|---|---|
| Người pilot | Dương T. L |
| Ngày giờ | 28/07/2026 |
| Vấn đề phát hiện | Không phát hiện vấn đề gì |
| Điều chỉnh sau pilot | Không có điều chỉnh gì |

### 1.5. Bảng người tham gia chính thức (5 người)


| # | Vai trò | Tên | Liên hệ | Ghi chú |
|---|---|---|---|---|
| P1 | Student FIT | Trương C. T. P | 036\*\*\*\*568 | |
| P2 | Student FIT | Võ H. T | 091\*\*\*\*907 | |
| P3 | Student FIT | Nguyễn V. M. Q | 077\*\*\*\*444 | |
| P4 | Student | Võ L. H. T | 076\*\*\*\*492 | |
| P5 | Student FIT | Lưu H | 090\*\*\*\*908 | |

---

## PHASE 2 — Session Observation Notes


### Session P1
- **Thời gian bắt đầu/kết thúc:** 23:05 – 23:10
- **Task success:** Partial
- **Time on task:** 5:30
- **Số lỗi/hesitation quan sát được:** 9
- **Ghi chú quan sát (think-aloud, friction points):**
  - Hành vi: P1 nhìn lướt qua khu vực dưới header vài giây, chưa
    thao tác ngay, phải nhìn kỹ hơn mới nhận ra có tab.     
    Participant nói: "Thiếu padding một khoảng bên dưới header, với lại
    màu sắc các tab khá giống với background (màu xám) nên nhìn liền
    mạch, làm mình chưa nhận biết được các tab này cho đến khi nhìn kỹ
    hơn một chút."  
  
  - Hành vi: P1 di chuyển chuột qua nhiều vị trí trong dòng sự
    kiện trước khi tìm đúng vị trí click (icon con mắt).     
    Participant nói: "Theo trải nghiệm trước đây, mình thường ấn vào một
    vị trí bất kỳ miễn là nó nằm trong ô sự kiện thì sẽ được chuyển sang
    trang xem chi tiết. Tuy nhiên mình phải di chuyển con chuột đến nút
    view hình con mắt thì mới xem được chi tiết. Thêm vào đó, màu sắc
    của icon này khá trùng với màu chữ, thoạt nhìn mình không nghĩ nó
    có thể click được."

  - Hành vi: P1 cuộn ngang bảng sự kiện nhiều lần để xem hết cột;
    ban đầu không thao tác cuộn cho đến khi chú ý thấy thanh cuộn ngang
    bên dưới.   
    Participant nói: "Số lượng cột của một dòng sự kiện khá nhiều, khiến
    mình phải cuộn ngang qua để xem. Nhưng cũng chính vì vậy, mình sẽ
    không ghi nhớ được tất cả thông tin của sự kiện mà mình muốn xem.
    Thêm vào đó cột action tuy cố định nhưng trùng hợp có màu sắc y hệt
    nên nhìn liền mạch, mình nghĩ bảng này chỉ gồm 4 cột như trên ảnh
    thôi. Do đó ngay lúc đầu sử dụng, mình không hề biết có thể cuộn
    ngang để xem các thông tin khác cho đến khi mình chú ý đến thanh
    cuộn ngang bên dưới."

  - Hành vi: P1 tìm cột số lượng học sinh/giảng viên/thời gian
    đăng ký bằng cách cuộn ngang; các cột này nằm ở cuối và không liền
    kề nhau.    
    Participant nói: "Bảng sự kiện không ưu tiên những thông tin quan
    trọng. Là một người quản lý sự kiện, có lẽ thứ mình quan tâm chính
    là số lượng học sinh, giảng viên, thời gian đăng ký. Những thông tin
    khác, có lẽ chỉ cần đọc thấy tên sự kiện là mình cũng có thể nhớ
    được rồi vì mình là người tạo và quản lý nó mà, nếu không nhớ thì
    làm sao quản lý được. Tuy nhiên, những thông tin này lại xuất hiện
    ở sau cùng hoặc bị che lấp bởi giới hạn chiều rộng màn hình. Thêm
    vào đó, một trong số chúng không xếp cạnh nhau làm mất tính mạch
    lạc khi quản lý một sự kiện nào đó."

  - Hành vi: P1 search một sự kiện, vào trang chi tiết, sau đó
    bấm quay lại trang quản lý chung; danh sách hiển thị là danh sách
    mặc định thay vì giữ lại kết quả search trước đó. 
    Participant nói: "Khi search một sự kiện, mình vào trang chi tiết
    của nó, sau đó quay trở lại trang quản lý chung. Tuy nhiên, thứ
    mình thấy là danh sách sự kiện mặc định do hệ thống sắp xếp thay vì
    thanh search hiển thị thông tin mình search và danh sách kết quả."

  - Hành vi: P1 click lần lượt vào nút "All status" và "All time",
    kỳ vọng hành vi giống nút "+Add Event" (chuyển trang), nhưng lại
    thấy danh sách thả xuống xuất hiện.   
    Participant nói: "Nút lọc sự kiện không thể hiện rõ hành vi. Khi
    nhìn vào 2 nút All status và All time, mình nghĩ mình chỉ cần click
    vào là sẽ có kết quả giống như cách những nút khác hoạt động. Ví dụ,
    ấn nút +Add Event thì nó sẽ chuyển sang trang thêm sự kiện mới. Tuy
    nhiên, 2 nút này lại hiện ra danh sách thả xuống, thứ mà mình không
    kỳ vọng trước đó."

  - Hành vi: P1 nhìn ô "Go to page" và thử click trực tiếp vào
    như một nút bấm; khi di chuột vào mới thấy con trỏ đổi hình dạng.    
    Participant nói: "Thoạt đầu, mình cứ tưởng đây là một nút bấm do nó
    có giao diện và cách trình bày khá giống với các nút khác. Tuy
    nhiên, khi di chuột vào mình thấy con trỏ chuột đổi sang hình dạng
    khác và thử ấn vào thì mới biết đây là một ô để nhập số trang mình
    mong muốn đến."

  - Hành vi: P1 đổi số dòng hiển thị từ 5 lên 100, sau đó phải
    cuộn dài xuống cuối trang mới tới được thanh chuyển trang.    
    Participant nói: "Thanh chuyển trang được đặt bên dưới danh sách.
    Ban đầu, mặc định là 5 dòng sự kiện được trình bày trên bảng thì vị
    trí đặt bên dưới này không có vấn đề gì. Tuy nhiên, khi mình chọn
    số lượng là 100 dòng thì thanh này được đẩy xuống tít bên dưới
    khiến mình phải cuộn rất lâu và tốn thời gian thì mới cuộn tới nếu
    mình muốn chuyển trang hoặc chỉnh lại số dòng."

  - P1 nhận thấy trên giao diện, ngày đăng ký của một sự kiện có thể
    diễn ra sau ngày check-in của chính sự kiện đó — nghi vấn thiếu validate
    logic thời gian giữa 2 trường ngày. Cần kiểm tra lại độc lập (không tính
    là usability finding, sẽ báo riêng vào Bug & Usability Findings Log §7
    với Type = Bug).
- **Phản hồi SUS/UEQ-S (điểm từng câu):** 

| STT | Câu | Điểm (1–5) |
| :---: | --- | :---: |
| 1 | Tôi nghĩ mình sẽ muốn dùng hệ thống này thường xuyên. | 1 |
| 2 | Tôi thấy hệ thống phức tạp một cách không cần thiết. | 3 |
| 3 | Tôi thấy hệ thống dễ sử dụng. | 1 |
| 4 | Tôi nghĩ mình cần người am hiểu kỹ thuật hỗ trợ mới dùng được. | 1 |
| 5 | Tôi thấy các chức năng trong hệ thống kết hợp nhịp nhàng với nhau. | 3 |
| 6 | Tôi thấy hệ thống có quá nhiều điểm thiếu nhất quán. | 5 |
| 7 | Tôi nghĩ hầu hết mọi người sẽ học cách dùng hệ thống này rất nhanh. | 2 |
| 8 | Tôi thấy hệ thống rất rườm rà, bất tiện khi sử dụng. | 5 |
| 9 | Tôi cảm thấy rất tự tin khi sử dụng hệ thống. | 5 |
| 10 | Tôi phải học rất nhiều thứ trước khi có thể bắt đầu dùng. | 1 |
- **Trả lời probe questions:**
  - Q1: T thấy mình làm đúng
  - Q2: Vẫn biết cách quay lại
  - Q3: Tốc độ bình thường, không nhanh không chậm
  - Q4: Chắc cũng đúng
- **Link recording:** [Video user1](https://youtu.be/wuI8epnUKYI)

### Session P2
- **Thời gian bắt đầu/kết thúc:** 14:10 – 14:12
- **Task success:** Completed
- **Time on task:** 01:15
- **Số lỗi/hesitation quan sát được:** 1
- **Ghi chú quan sát (think-aloud, friction points):**
  - Người dùng bối rối lúc review student không biết phải nhấn xác nhận ở đâu, mất vài giây để suy nghĩ
  - Khi vào phần check-in, người dùng không biết phải lấy barcode ở đâu nên đã checkin với kí tự ngẫu nhiên ở lần đầu tiên; phải có chỉ dẫn mới có thể tìm được code.
- **Phản hồi SUS/UEQ-S (điểm từng câu):**

| # | Câu | Điểm (1–5) |
|---|-----|------------|
| 1 | Tôi nghĩ mình sẽ muốn dùng hệ thống này thường xuyên. | 3 |
| 2 | Tôi thấy hệ thống phức tạp một cách không cần thiết. | 3 |
| 3 | Tôi thấy hệ thống dễ sử dụng. | 4 |
| 4 | Tôi nghĩ mình cần người am hiểu kỹ thuật hỗ trợ mới dùng được. | 1 |
| 5 | Tôi thấy các chức năng trong hệ thống kết hợp nhịp nhàng với nhau. | 3 |
| 6 | Tôi thấy hệ thống có quá nhiều điểm thiếu nhất quán. | 4 |
| 7 | Tôi nghĩ hầu hết mọi người sẽ học cách dùng hệ thống này rất nhanh. | 2 |
| 8 | Tôi thấy hệ thống rất rườm rà, bất tiện khi sử dụng. | 2 |
| 9 | Tôi cảm thấy rất tự tin khi sử dụng hệ thống. | 5 |
| 10 | Tôi phải học rất nhiều thứ trước khi có thể bắt đầu dùng. | 1 |
- **Trả lời probe questions:**
  - Q1: T chắc chắn mình làm đúng
  - Q2: Thấy cũng dễ hiểu, vẫn biết cách quay lại
  - Q3: Tốc độ nhanh, vừa ổn
  - Q4: Không hoàn toàn tin tưởng
- **Link recording (nếu có):** [Video user2](https://youtu.be/p3lxP7p3pfs)

### Session P3
- **Thời gian bắt đầu/kết thúc:** 8:25 - 8:29
- **Task success:** Completed
- **Time on task:** 04:00
- **Số lỗi/hesitation quan sát được:** 1
- **Ghi chú quan sát (think-aloud, friction points):**
  - Nhìn qua các tab phía trên nhiều lần, không thao tác ngay, có vẻ đang tìm chức năng duyệt đăng ký. Không biết phải chấp nhận những học sinh hợp lệ ở đâu, phần tab ở trên khiến mình khó hiểu, không rõ tab nào dẫn tới màn hình duyệt đăng ký."

  - Mình mất vài giây vì không biết như thế nào là học sinh hay giảng viên hợp lệ để xét duyệt — không thấy tiêu chí hay trạng thái nào giúp phân biệt trước khi bấm duyệt.

  - Tìm kiếm quanh màn hình check-in, không xác định được cách lấy mã code.
- **Phản hồi SUS/UEQ-S (điểm từng câu):**

| # | Câu | Điểm (1–5) |
|---|-----|------------|
| 1 | Tôi nghĩ mình sẽ muốn dùng hệ thống này thường xuyên. | 3 |
| 2 | Tôi thấy hệ thống phức tạp một cách không cần thiết. | 2 |
| 3 | Tôi thấy hệ thống dễ sử dụng. | 4 |
| 4 | Tôi nghĩ mình cần người am hiểu kỹ thuật hỗ trợ mới dùng được. | 1 |
| 5 | Tôi thấy các chức năng trong hệ thống kết hợp nhịp nhàng với nhau. | 3 |
| 6 | Tôi thấy hệ thống có quá nhiều điểm thiếu nhất quán. | 3 |
| 7 | Tôi nghĩ hầu hết mọi người sẽ học cách dùng hệ thống này rất nhanh. | 5 |
| 8 | Tôi thấy hệ thống rất rườm rà, bất tiện khi sử dụng. | 2 |
| 9 | Tôi cảm thấy rất tự tin khi sử dụng hệ thống. | 4 |
| 10 | Tôi phải học rất nhiều thứ trước khi có thể bắt đầu dùng. | 1 |
- **Trả lời probe questions:**
  - Q1: Thực hiện đúng nhưng mà nhiều chỗ khó hiểu quá
  - Q2: Mò 1 chút vẫn ra, chỗ barcode làm t nghĩ nếu không có gợi ý thì khó làm được
  - Q3: Chậm hơn t nghĩ
  - Q4: Không tin
- **Link recording (nếu có):** [Video user 3](https://youtu.be/X572lo60YqM)

### Session P4
- **Thời gian bắt đầu/kết thúc:** 21:00-21:01
- **Task success:** Completed
- **Time on task:** 01:00
- **Số lỗi/hesitation quan sát được:** 0
- **Ghi chú quan sát (think-aloud, friction points):**
  - Ban đầu người dùng bấm vào tên của sự kiện nhưng không hiện chi tiết, làm người dùng hơi bối rối
  - Người dùng thấy trong review chỉ hiện theo hàng, không dẫn đến thông tin chi tiết người dùng, không biết làm sao để xem có hợp lệ không

- **Phản hồi SUS/UEQ-S (điểm từng câu):**

| # | Câu | Điểm (1–5) |
|---|-----|------------|
| 1 | Tôi nghĩ mình sẽ muốn dùng hệ thống này thường xuyên. |2|
| 2 | Tôi thấy hệ thống phức tạp một cách không cần thiết. |3 |
| 3 | Tôi thấy hệ thống dễ sử dụng. |3|
| 4 | Tôi nghĩ mình cần người am hiểu kỹ thuật hỗ trợ mới dùng được. |1|
| 5 | Tôi thấy các chức năng trong hệ thống kết hợp nhịp nhàng với nhau. |2|
| 6 | Tôi thấy hệ thống có quá nhiều điểm thiếu nhất quán. |5|
| 7 | Tôi nghĩ hầu hết mọi người sẽ học cách dùng hệ thống này rất nhanh. |2 |
| 8 | Tôi thấy hệ thống rất rườm rà, bất tiện khi sử dụng. |3|
| 9 | Tôi cảm thấy rất tự tin khi sử dụng hệ thống. |4|
| 10 | Tôi phải học rất nhiều thứ trước khi có thể bắt đầu dùng. |1|
- **Trả lời probe questions:**
  - Q1: Ngoài phần duyệt sinh viên thì những phần còn lại cũng rõ ràng
  - Q2: Làm sai thì quan sát một lúc vẫn ra được
  - Q3: Nhanh hơn t nghĩ, chắc do t thông minh chứ thấy web hơi rườm rà
  - Q4: Cũng tạm tin
- **Link recording (nếu có):** [Video user 4](https://youtu.be/NpDySOcA9lA)

### Session P5
- **Thời gian bắt đầu/kết thúc:**  21:00 - 21:09
- **Task success:** Completed
- **Time on task:** 08:41
- **Số lỗi/hesitation quan sát được:** 2
- **Ghi chú quan sát (think-aloud, friction points):** 
  - Loay hoay ngay từ đầu, không tìm được đường vàotrang riêng dành cho admin.
  - Bấm vào tên sự kiện trong danh sách, chờ trangchi tiết hiện ra nhưng không có phản hồi.
  - Mở danh sách người đăng ký, lọc theo trạng tháimPending, sau đó tìm quanh màn hình không thấy nút duyệt; cuối cùng mở User Guide để đọc hướng dẫn.
  - Tìm mã code của học sinh để check-in, không thấy ở đâu; định thoát ra đăng ký một tài khoản sinh viên mới để lấy mã code.
- **Phản hồi SUS/UEQ-S (điểm từng câu):**

| # | Câu | Điểm (1–5) |
|---|-----|------------|
| 1 | Tôi nghĩ mình sẽ muốn dùng hệ thống này thường xuyên. | 1 |
| 2 | Tôi thấy hệ thống phức tạp một cách không cần thiết. | 5 |
| 3 | Tôi thấy hệ thống dễ sử dụng. | 3 |
| 4 | Tôi nghĩ mình cần người am hiểu kỹ thuật hỗ trợ mới dùng được. | 2 |
| 5 | Tôi thấy các chức năng trong hệ thống kết hợp nhịp nhàng với nhau. | 2 |
| 6 | Tôi thấy hệ thống có quá nhiều điểm thiếu nhất quán. | 4 |
| 7 | Tôi nghĩ hầu hết mọi người sẽ học cách dùng hệ thống này rất nhanh. | 2 |
| 8 | Tôi thấy hệ thống rất rườm rà, bất tiện khi sử dụng. | 4 |
| 9 | Tôi cảm thấy rất tự tin khi sử dụng hệ thống. | 3 |
| 10 | Tôi phải học rất nhiều thứ trước khi có thể bắt đầu dùng. | 2 |
- **Trả lời probe questions:**
  - Q1: Không có chỗ nào không chắc. Không có nút nào gây khó hiểu
  - Q2: Tự tìm cách được
  - Q3: Tốc độ chậm hơn t nghĩ
  - Q4: Thấy cũng đáng tin
- **Link recording (nếu có):** [Video user 5](https://youtu.be/FPgPtLPVer4)

---

## PHASE 3 — Collect, Analyse & Report

### 3.1. Bảng điểm SUS/UEQ-S chi tiết (10 câu, thang 1–5)

> Công thức SUS chuẩn: câu lẻ (1,3,5,7,9) = điểm – 1; câu chẵn (2,4,6,8,10) = 5 – điểm; tổng × 2.5 = điểm/100.

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
| **Điểm SUS/100** | **42.5** | **65.0** | **75.0** | **50.0** | **35.0** |

| | Trung bình | Min | Max |
|---|---|---|---|
| **SUS/100** | **53.5** | **35.0 (P5)** | **75.0 (P3)** |

### 3.2. Bảng Metrics tổng hợp

| Participant | Task Success | Time on task | Số lỗi/hesitation |
|---|---|---|---|
| P1 | Partial | 05:30 | 9 |
| P2 | Completed | 01:15 | 1 |
| P3 | Completed | 04:00 | 1 |
| P4 | Completed | 01:00 | 0 |
| P5 | Completed | 08:41 | 2 |
| **Trung bình / Tỷ lệ** | **4/5 completed (80.0%)** | **04:26** | **2.6** |

### 3.3. Ranked Findings (Severity 0–4)

| # | Finding (pain point) | Type | Phạm vi | Severity | Người gặp | Đề xuất khắc phục |
|---|---|---|---|---|---|---|
| 1 | Không tìm thấy mã code/QR để check-in — có người gần như bỏ cuộc, định tạo tài khoản sinh viên mới chỉ để lấy mã, cũng như bị rối khi viết là barcode nhưng trong danh sách lại là Member code | Usability | Systemic (P3, P5) | 4 | P3, P5 | Hiển thị rõ nút/khu vực "Nhập Member code" ngay trên màn hình Check-in, có label tường minh, không yêu cầu suy luận |
| 2 | Không tìm được nơi duyệt đăng ký đang Pending — phải mở User Guide mới biết (P5), tab điều hướng gây khó hiểu (P3) | Usability | Systemic (P3, P5) | 4 | P3, P5 | Thêm badge số lượng "Pending" ngay trên tab liên quan; đổi tên tab rõ nghĩa hơn (vd "Duyệt đăng ký") thay vì tên chung chung |
| 3 | Bấm vào tên sự kiện không mở chi tiết — phải dùng đúng icon con mắt, gây kỳ vọng sai (khác hành vi quen thuộc) | Usability | Systemic (P1, P4, P5) | 3 | P1, P4, P5 | Cho phép click cả dòng (row-click) để mở chi tiết, giữ icon mắt như lối tắt phụ, không phải lối duy nhất |
| 4 | Kết quả search bị mất khi quay lại danh sách sau khi xem chi tiết sự kiện | Bug | Isolated | 3 | P1 | Giữ lại query/filter state khi back về danh sách (lưu ở URL params hoặc session state) |
| 5 | Thiếu validate: ngày đăng ký có thể diễn ra sau ngày check-in | Bug | Isolated | 3 | P1 | Thêm validate ràng buộc registration date ≤ check-in date ở form Add/Edit Event |
| 6 | Web chậm liên tục, phải chờ rất lâu để load trang nhưng không có loading state | Usability | Isolated | 3 | P3 | Thêm spinning để người dùng biết đang tải trang, áp dụng Lazy Loading và Caching dữ liệu. |
| 7 | Danh sách Review chỉ hiện dạng hàng, không link tới thông tin chi tiết người review để xác minh hợp lệ | Usability | Isolated | 2 | P4 | Thêm link/click-through từ mỗi review sang thông tin participant liên quan |
| 8 | Bảng sự kiện có quá nhiều cột, phải cuộn ngang, không biết có thể cuộn cho đến khi để ý thanh cuộn; cột quan trọng (số lượng học sinh/giảng viên/thời gian đăng ký) nằm cuối, không liền kề | Usability | Isolated | 2 | P1 | Ưu tiên hiển thị cột quan trọng ở đầu bảng; thêm chỉ báo trực quan (vd shadow/arrow) báo hiệu có thể cuộn ngang |
| 9 | Nút "All status"/"All time" hiện dropdown thay vì điều hướng, không khớp kỳ vọng dựa trên hành vi các nút khác | Usability | Isolated | 2 | P1 | Thêm icon mũi tên (chevron) trên các nút dropdown để phân biệt với nút điều hướng |
| 10 | Header/tab phía trên thiếu padding, màu tab gần giống màu nền, khó nhận biết ngay khi vào trang | Usability | Isolated | 2 | P1 | Tăng contrast màu tab active/inactive với nền; thêm khoảng cách (padding) dưới header |
| 11 | Thanh chuyển trang bị đẩy xuống rất xa, gây khó khăn khi chọn hiển thị 100 dòng/trang phải cuộn xuống dưới | Usability | Isolated | 1 | P1 | Cố định (sticky) thanh pagination ở cuối viewport thay vì cuối bảng |

### 3.4. Prioritised Recommendations

[Ưu tiên cao nhất] — Làm rõ luồng check-in (đổi thành entetr member code thay vì barcode) và luồng duyệt đăng ký (vị trí tab, badge Pending) — đây là 2 finding Systemic với severity 4, trực tiếp chặn việc hoàn thành nhiệm vụ chính của task, ảnh hưởng 2/5 participant mỗi finding (liên kết Finding #1, #2).

[Ưu tiên cao] — Đổi hành vi click item sự kiện: cho phép click cả dòng thay vì chỉ icon mắt — finding Systemic, ảnh hưởng 3/5 participant, gây kỳ vọng sai lặp lại nhiều lần (liên kết Finding #3).

[Ưu tiên trung bình] —  Chỉnh sửa logic ngày đăng ký/check-in và giữ lại state search khi back — cả hai đều là vấn đề chức năng (Bug).

[Ưu tiên trung bình] — Bổ sung tiêu chí hợp lệ trong danh sách chờ duyệt và link review → chi tiết participant, giúp admin ra quyết định duyệt nhanh và chính xác hơn (liên kết Finding #6, #7).

[Ưu tiên thấp] — Các cải tiến UI nhỏ: contrast tab/header, chỉ báo cuộn ngang, phân biệt input "Go to page" với nút bấm, cố định thanh pagination (liên kết Finding #8–12).

### 3.5. Kết luận Usability

Điểm SUS trung bình của 5 participant là 53.5/100, thấp hơn benchmark ngành (68/100) khoảng 14.5 điểm, xếp vào mức "below average" theo thang Bangor. Đáng chú ý là độ phân tán rất lớn (35–75), cho thấy vấn đề không nằm ở toàn bộ hệ thống một cách đồng đều mà tập trung vào một số điểm chặn cụ thể trong luồng task: 3 finding có mức Systemic — không biết mã code chec-in là gì, không tìm thấy nơi duyệt đăng ký, và hành vi click sự kiện không nhất quán — đều liên quan trực tiếp đến khả năng hoàn thành được nhiệm vụ chính (duyệt đăng ký + check-in) mà task scenario yêu cầu, không phải các vấn đề thẩm mỹ phụ. Đề xuất tổng thể: ưu tiên khắc phục 3 finding Systemic trước (Finding #1–3) vì chúng ảnh hưởng nhiều người và chặn trực tiếp task chính, sau đó mới xử lý các cải tiến UI nhỏ lẻ còn lại.