Khách hàng (Customer):

- Vai trò: Người dùng cuối (end-user), khởi tạo toàn bộ quy trình bằng cách tương tác với hệ thống qua giao diện (web/app). Họ cung cấp input như tiêu chí tìm kiếm, thông tin cá nhân, và chi tiết thanh toán.
- Lý do tham gia: Là actor chính trong quy trình đặt phòng, đại diện cho người dùng bên ngoài hệ thống. Không xử lý logic nội bộ mà chỉ gửi/nhận thông tin.


Hệ thống Đặt Phòng (Booking System):

- Vai trò: Thành phần frontend/middleware của hệ thống, xử lý giao diện người dùng (UI), thu thập input từ Customer, và điều phối các yêu cầu đến các đối tượng khác. Nó hiển thị kết quả, gửi notify, và xử lý luồng chính.
- Lý do tham gia: Làm cầu nối giữa người dùng và backend, đảm bảo trải nghiệm mượt mà. Đây là participant nội bộ, không phải actor thuần túy mà là lớp logic ứng dụng.


Lễ tân (Receptionist):

- Vai trò: Nhân viên lễ tân, tham gia ở các trường hợp extend (tùy chọn), như nhận notify về đặt phòng mới và xác nhận thủ công (ví dụ: kiểm tra giấy tờ hoặc xử lý đặt phòng lớn).
- Lý do tham gia: Đại diện cho yếu tố con người trong hệ thống, xử lý các tình huống không tự động (như VIP hoặc vấn đề kỹ thuật). Chỉ tham gia nếu cần, để tránh làm phức tạp luồng chính.


Quản lý (Manager):

- Vai trò: Quản lý viên, tham gia phê duyệt trong các trường hợp đặc biệt (opt fragment), như đặt phòng lớn hoặc khuyến mãi. Họ nhận yêu cầu từ Receptionist và phản hồi phê duyệt/từ chối.
- Lý do tham gia: Đảm bảo kiểm soát quản lý, đặc biệt với các giao dịch quan trọng. Đây là actor cấp cao, chỉ can thiệp khi cần để duy trì an toàn và chính sách.


Admin (Administrator):

- Vai trò: Quản trị viên hệ thống, xử lý xác thực user (validate user) nếu cần, như kiểm tra tài khoản khách hàng có hợp lệ hoặc bị khóa không.
- Lý do tham gia: Quản lý bảo mật và quyền truy cập. Tham gia ở đầu luồng để xác thực, ngăn chặn lạm dụng (ví dụ: user giả mạo).


Server (Database Server):

- Vai trò: Thành phần backend/database, xử lý lưu trữ và truy vấn dữ liệu (query phòng trống, cập nhật trạng thái phòng, xử lý thanh toán). Nó đảm bảo tính nhất quán dữ liệu (atomic transactions).
- Lý do tham gia: Là "tim" của hệ thống, xử lý logic cốt lõi như kiểm tra availability và sync dữ liệu. Được coi là actor external nếu tích hợp với hệ thống bên thứ ba (như payment gateway).
