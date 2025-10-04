## Use Case 1: Tìm kiếm phòng (Search Rooms)
- **ID**: UC-03
- **Tên**: Search Rooms
- **Mô tả ngắn**: Khách hàng tìm kiếm các phòng trống dựa trên tiêu chí như ngày lưu trú, loại phòng và tiện nghi.
- **Actors**: Customer (Primary), System (Secondary).
- **Pre-conditions**: Khách hàng đã truy cập hệ thống (không cần đăng nhập); Hệ thống có dữ liệu phòng cập nhật.
- **Post-conditions**: Hiển thị danh sách phòng phù hợp; Không thay đổi dữ liệu hệ thống.
- **Main Flow**:
  1. Khách hàng nhập tiêu chí tìm kiếm (ngày check-in/check-out, số lượng người, loại phòng: tiêu chuẩn/phòng suite, giá cả).
  2. Hệ thống kiểm tra cơ sở dữ liệu và lọc phòng trống phù hợp.
  3. Hệ thống hiển thị danh sách phòng (hình ảnh, giá, tiện nghi, đánh giá).
  4. Khách hàng có thể lọc thêm hoặc xem chi tiết phòng.
  5. Use Case kết thúc (chuyển sang Book Room nếu cần).
- **Alternative Flows**:
  - 3a. Không có phòng phù hợp: Hệ thống gợi ý phòng tương tự hoặc ngày thay thế (ví dụ: ngày gần nhất có sẵn).
- **Exceptions**:
  - 1a. Tiêu chí không hợp lệ (ví dụ: ngày check-out trước check-in): Hệ thống hiển thị thông báo lỗi và yêu cầu nhập lại.

## Use Case 2: Đặt phòng (Book Room)
- **ID**: UC-01
- **Tên**: Book Room
- **Mô tả ngắn**: Khách hàng chọn phòng từ kết quả tìm kiếm và hoàn tất đặt phòng với thông tin cá nhân và thanh toán.
- **Actors**: Customer (Primary), System (Secondary).
- **Pre-conditions**: Khách hàng đã thực hiện Search Rooms thành công; Khách hàng đã đăng nhập (hoặc tạo tài khoản mới).
- **Post-conditions**: Đặt phòng được xác nhận; Trạng thái phòng cập nhật thành "Đã đặt"; Gửi email xác nhận cho khách.
- **Main Flow**:
  1. Khách hàng chọn phòng từ danh sách tìm kiếm (<<include>> Search Rooms).
  2. Hệ thống hiển thị chi tiết phòng và yêu cầu nhập thông tin (tên, email, số điện thoại, phương thức thanh toán).
  3. Khách hàng xác nhận và thực hiện thanh toán (hoặc đặt cọc nếu áp dụng).
  4. Hệ thống xử lý thanh toán, tạo mã đặt phòng và gửi email xác nhận.
  5. Use Case kết thúc.
- **Alternative Flows**:
  - 2a. Khách hàng thay đổi phòng: Quay lại bước 1 để chọn phòng khác.
- **Exceptions**:
  - 3a. Thanh toán thất bại (thẻ không hợp lệ): Hệ thống hủy đặt tạm thời, thông báo lỗi và cho phép thử lại hoặc hủy.
