### **(Bài tập tổng hợp) Ngày Đầu Thực Tập Dev Tại Công Ty Công Nghệ** 

### **Phần A – Thiết lập Profile và Bookmark chuẩn Dev**

1. **Giải thích bằng đúng khái niệm đã học: nếu tiếp tục dùng chung 1 Profile cho cả GitHub cá nhân và GitHub công ty, điều gì xảy ra khi đăng nhập song song cả hai?**  
+  Làm rối loạn giữa tab GitHub cá nhân và GitHub công ty  
+  Mở đồng thời 2 tài khoản GitHub khác nhau trên 1 cửa sổ sẽ bị tự động văng.  
+  Sẽ bị lộ tin nhắn hoặc lịch sử Search,...

2. **Áp dụng Mô hình 3 Profile chuẩn Developer vào bối cảnh công ty:**

| Profile | Tên Profile | Mục đích |
| ----- | ----- | ----- |
| 1 | Personal | Sử dụng cho công việc cá nhân, các bảo mật riêng tư,...  |
| 2 | Company | Sử dụng cho công việc trên công ty, các tài khoàn đăng nhập vào công ty,... |
| 3 | Entertainment | Xem phim, nghe nhạc,... |

3. **Thiết kế cấu trúc Bookmark gồm 3 thư mục, mỗi thư mục liệt kê 2 trang web nên lưu (theo đúng logic phân loại đã học).**  
- 01\_work\_Dev (Github, StackOverflow)  
- 02\_study\_PTIT (QLĐT, Microsoft Team)  
- 03\_Tools (JSON Formatter, WhatFont)

4. **Đồng nghiệp mượn máy bạn 5 phút để tra cứu nhanh — bạn cho họ dùng chế độ/Profile nào để không lộ dữ liệu cá nhân? Giải thích ngắn gọn.**  
- Sẽ cho bạn dùng chế độ Guest Profile vì nó sẽ tự động hủy toàn bộ lịch sử mà mình làm trước đó.

### 

### 

### 

### **Phần B – Chọn đúng Extension hỗ trợ**

1. **Với đường link API JSON thô mentor gửi, bạn cài Extension thuộc nhóm nào trong 3 nhóm (Dev Suite / Productivity Suite / Security Suite)? Gọi đúng tên tiện ích và giải thích vì sao 2 nhóm còn lại không phù hợp.**  
- Thuộc nhóm Security Suite  
- Tên tiện ích: JSON Viewer/ Formatter  
    
- 2 nhóm còn lại không phù hợp vì:   
- Productivity Suite  
+ Mục đích: Hỗ trợ quản lý công việc, ghi chú, kiểm tra lỗi ngữ pháp  
+ Lý do không phù hợp: Các tiện ích này không có tính năng phân tích cú pháp hay soi phông chữ và có chế độ ban đêm. Nên không giải quyết được vấn đề dữ liệu kỹ thuật từ API  
  .  
- Security Suite  
+ Mục đích: Chặn quảng cáo, theo dõi , quét mã độc trang web, quản lý mật khẩu   
+ Lý do không phù hợp: Nhóm này chỉ đóng vai trò bảo vệ hoặc lọc nội dung nguy hiểm.

     2\.   **Sau khi cài, bạn cấu hình quyền Site Access là On click hay On all sites? Giải thích theo đúng quy tắc quản trị Extensions đã học.**

- Sau khi cài, nên cấu hình quyền On click vì: hạn chế quyền đọc dữ liệu web của Extension thay vì chọn On all sites vì nó sẽ đọc hết tất cả từ web.

### 

### **Phần C – Phân tích luồng HTTP Request**

1. **Khi gõ test.internal-tool.com và nhấn Enter, liệt kê đúng thứ tự 4 giai đoạn xử lý (từ lúc gõ địa chỉ đến khi trang hiển thị).**  
- DNS Lookup: trình duyệt yêu cầu DNS tra cứu IP của test.internal-tool.com 

- TCP / TLS Handshake: trình duyệt kết nối thành công tới IP của trang web.

- HTTP Request: trình duyệt sẽ gửi yêu cầu lấy nội dung từ máy chủ  
     
- Browser Render: trình duyệt nhận dữ liệu tải về, phân tích HTML và CSS để làm cây DOM và CSSOM, sau đó tính toán bố cục Layout và vẽ các ảnh lên màn hình để người dùng nhìn thấy giao diện hoàn chỉnh. 

2. **So sánh 2 mã trạng thái và hướng debug ban đầu:**

| Mã trạng thái | Ý nghĩa | Lỗi nằm ở đâu ? | Hướng Debug ban đầu |
| ----- | ----- | ----- | ----- |
| 404 Not Found | không tìm thấy file đó, sai URL | Nằm ở phía máy cá nhân hoặc máy khác do nhập sai URL hoặc trang web đó đã bị xóa | Nhập lại chính xác đường dẫn URL, cần nhấn Ctrl \+ F5 để xóa đi file đã lưu trong Cache để trình duyệt cập nhật lại file mới |
| 500 Internal Server Error | lỗi Server | Nằm ở phía máy chủ mặc dù đã đúng địa chỉ IP, có thể máy chủ bị sập hoặc quá tải | Ktra lại các code trong file, xem có chỗ nào báo lỗi màu đỏ  không, |

   ### 

###  **3\. Trong 4 Tab DevTools (Elements / Console / Network / Application), bạn mở Tab nào để xem mã trạng thái HTTP của trang? Vì sao không chọn các Tab còn lại?**

- Mở Tab NetWork để xem mã trạng thái vì:  
- Tab Elements: dùng để chỉnh sửa kích cỡ chữ, thay đổi màu sắc, xem các đoạn code.  
- Console: viết code Javascript, CSS,...  
- Application: dùng để xem các tên miền, xóa cookies,....

### 

### **Phần D – Chẩn đoán Cache và Cookies**

1. **Dev vừa sửa CSS nhưng F5 vẫn thấy giao diện cũ. Chẩn đoán đúng nguyên nhân và nêu chính xác thao tác khắc phục đã học.**  
- Nguyên nhân là do file CSS cũ đã đc lưu vào Cache trước đó nên trình duyệt sẽ lấy file cũ đó để hiện ra màn hình chứ không lấy file đã sửa lại.  
- Cách khắc phục: nhấn Ctrl \+ shil \+ R hoặc Ctrl \+ F5 để xóa đi file cũ đã lưu trong Cache và trình duyệt sẽ cập nhật lại file mới.

2. **Trong tab Application, Cookie session\_id không có dấu tích ở cột HttpOnly. Nêu rủi ro bảo mật cụ thể và tên loại tấn công có thể xảy ra.**  
- Rủi ro: tấn công mã độc XSS để đánh cắp Session Cookie thông qua mã tệp lệnh JavaScript (document.cookie)  
- Tên loại tấn công: XSS (Cross-Site Scripting)   
    
3. **Bạn chỉ muốn đăng xuất (xóa phiên đăng nhập) nhưng vẫn giữ nguyên Cache ảnh/CSS để trang load nhanh — bạn thao tác gì (khác với Clear toàn bộ Browsing Data)?**  
- Nhấn F12 rồi chuyển sang tab Application rồi tìm mục Storage, sau đó nhấp vào Cookies  \> Chọn tên miền  \> Nhấn vào biểu tượng Clear all cookies (biểu tương có ba dấu bằng và 1 dấu x)  
- Nhấn F5 để tải lại trang, toàn bộ ảnh, CSS trong bộ nhớ đệm vẫn được giữ nguyên. 

### **Phần E – Debug bằng Inspect Element và Network Tab**

1. **Nút "Đăng nhập" bị lệch màu so với thiết kế. Nêu đúng thao tác để thử sửa màu trực tiếp trên trình duyệt nhằm xác nhận đúng mã màu trước khi báo lại cho Dev.**  
- Nhấp chuột phải vào nút "Đăng nhập" \> chọn Inspect để mở tab Elements.  
- Tìm dòng mã màu: nhìn sang khung Styles bên cạnh, tìm thuộc tính color (màu chữ).  
- Thử màu mới: nhấp chuột vào mã màu cũ rồi dán mã màu theo yêu cầu, nhấn Enter để thấy màu mới.

**2\. Trên tab Network, một request API đang hiện dòng màu đỏ. Áp dụng đúng Quy trình 4 Bước Debugging đã học, viết lại từng bước bạn sẽ làm.**

- B1: Kích hoạt F12 và Disable Cache: bật cả 2 để trình duyệt luôn tải mã mới nhất từ server  
- B2: Định vị lỗi với tab Element  
- B3: Ktra mã trạng thái NetWork: 404/500   
- B4: Ktra Headers và Reponse Body ( soi chi tiết dữ liệu gửi đi và dữ liệu phản hồi từ máy chủ để xác nhận tính chính xác)

**3\. Bạn muốn chỉ xem các lời gọi API (không xem ảnh/CSS) và đảm bảo dữ liệu là bản mới nhất (không lấy từ bộ nhớ đệm) — nêu đúng 2 thao tác cần bật trên tab Network.**

1. Lọc chỉ xem lời gọi API:  
- Bấm chọn Fetch/XHR (để ẩn toàn bộ ảnh, CSS, JS, font )

      2\.   Đảm bảo lấy dữ liệu mới nhất (không dùng bộ nhớ đệm):

+ Tích chọn vào ô Disable cache để xóa file cũ và luôn lấy bản mới nhất