# 🏨 Hotel Booking System

##  Giới thiệu

**Hotel Booking System** là một mini project mô phỏng hệ thống quản lý đặt phòng khách sạn.
Khách hàng có thể tìm kiếm – đặt phòng – thanh toán, trong khi lễ tân và quản lý có thể quản lý booking, phòng và báo cáo.

🔹 **Mục tiêu:** Xây dựng một hệ thống cơ bản nhưng đầy đủ luồng chính từ **phân tích – thiết kế – lập trình – kiểm thử – báo cáo**.
🔹 **Quy mô:** Bài tập học tập (lab).



##  Artifacts đã xây dựng

### 🔹 Use Case Diagrams

* **Khách hàng (Customer):** đăng ký/đăng nhập, tìm kiếm phòng, đặt phòng, thanh toán, hủy booking, đánh giá.
* **Lễ tân (Receptionist):** tạo booking, xác nhận/hủy booking, check-in, check-out.
* **Quản lý khách sạn (Manager):** quản lý phòng, loại phòng, khuyến mãi, báo cáo doanh thu.
* **Admin:** quản lý hệ thống (users, phân quyền, báo cáo).
* **System:** xử lý dữ liệu, gửi thông báo, đồng bộ trạng thái phòng.

### 🔹 Sequence Diagrams

* Luồng khách hàng: đăng nhập → tìm phòng → đặt phòng → thanh toán → nhận xác nhận.
* Luồng lễ tân: quản lý booking → check-in/out khách.
* Luồng quản lý: quản lý loại phòng, giá, khuyến mãi → xem báo cáo.
* Luồng admin: giám sát hệ thống & báo cáo.
* System jobs: gửi email xác nhận, nhắc check-in, báo cáo doanh thu.

### 🔹 Form Login Code

* **Frontend:** `index.html`, `styles.css`, `main.js`.
* **Backend:** xử lý đăng nhập, kết nối MySQL.
* **Test:** Jest (unit test) + Selenium (integration test).

### 🔹 ERD & Database

Thực thể chính:
`Users, Rooms, RoomTypes, Bookings, Payments, Reviews, Notifications, Promotions, AuditLogs`.



## ⚙️ Quy trình làm việc

1. **Phân tích yêu cầu:** xác định actors, use case, sequence diagram.
2. **Thiết kế:** ERD, module backend, UI cơ bản.
3. **Lập trình & tích hợp:** API booking, login, check-in/out, quản lý phòng.
4. **Quản lý source code:** Git/GitHub, commit theo từng giai đoạn, tạo tag `v1.0`.
5. **Kiểm thử:** Unit test, integration test, manual test.
6. **Báo cáo:** Tổng hợp artifacts, viết report.


##  Hướng dẫn push code & tạo tag version

```bash
# Cấu hình Git (lần đầu)
git config --global user.name "Tên của bạn"
git config --global user.email "email@example.com"

# Thêm remote
git remote add origin https://github.com/n23dcpt084-byte/LAB01-CNPM.git

# Push code
git add .
git commit -m "Hoàn thiện v1.0 - Hotel Booking System"
git push origin main

# Tạo tag v1.0
git tag v1.0
git push origin v1.0
```


##  Kết luận

Dự án **Hotel Booking System** đã hoàn thành theo yêu cầu Lab.
 Có thể mở rộng thêm:

* Tích hợp thanh toán online (Momo, PayPal).
* Gửi email/SMS marketing cho khách hàng.
* Dashboard báo cáo nâng cao cho quản lý & admin.


