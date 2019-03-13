## Một số lệnh cơ bản Linux


| Lệnh | Chức năng | Ví dụ |
|-----------|-------------------|------------------|
| pwd | Hiển thị vị trí hiện tại trong hệ thống file.	| pwd|
| whoami | Hiển thị tên người dùng - hữu ích nhất nếu chuyển đổi người dùng bằng lệnh su và cần được nhắc nhở về tài khoản nào đang được sử dụng | whoami |
| ls | Cung cấp một danh sách file. Với tham số -a, lệnh hiển thị các file có tên bắt đầu bằng dấu chấm (ví dụ: .bashrc). Với tham số -l, lệnh hiển thị quyền, kích thước file và ngày/giờ cập nhật mới nhất.| ls, ls -a, ls -l |
| env | 	Hiển thị cài đặt môi trường người dùng (ví dụ: đường dẫn tìm kiếm, kích thước phần lịch sử được lưu lại, thư mục chính, v.v...) | env |
| echo | 	Lặp lại phần văn bản mà người dùng cung cấp hoặc hiển thị giá trị của một số biến. | echo, hello, $PATH |
| history | Liệt kê các lệnh đã đưa ra trước đó. | history |
| passwd  | Thay đổi mật khẩu. Lưu ý rằng các yêu cầu phức tạp có thể được thi hành.	| passwd |


### Tạo một thư mục mới

`mkdir name_folder`


Trong trường hợp nếu muốn tạo một thư mục chứa nhiều thư mục con, bạn có thể sử dụng tùy chọn "-p". Giả sử, bạn có thư mục foo và có quyền truy cập vào nó:

`mkdir -p /foo/bar/baz`

Lệnh trên sẽ tạo thư mục bar, thư mục baz nằm trong bar; bar và baz nằm trong /foo đã có.

Nếu muốn tìm kiếm thư mục hiện tại của bạn, bạn có thể sử dụng lệnh `pwd`.


Các hệ thống Linux cung cấp các lệnh để tạo các file. Người dùng có thể chọn trình soạn thảo văn bản mong muốn. Một số lệnh yêu cầu người dùng phải thành thạo trước khi sử dụng, còn những lệnh khác thì khá đơn giản.

| Lệnh | Chức năng | Ví dụ |
|------|-----------|-------|
| nano | Một trình chỉnh sửa văn bản dễ sử dụng, yêu cầu người dùng di chuyển trong file bằng các phím mũi tên và cung cấp các chuỗi điều khiển để định vị văn bản, lưu các thay đổi, v.v.	| nano myfile |
| vi | Một trình chỉnh sửa tinh vi hơn, cho phép người dùng nhập các lệnh để tìm và thay đổi văn bản, thực hiện các thay đổi tổng thể, v.v... | vi myfile |
| ex | Một trình soạn thảo văn bản được thiết kế cho các lập trình viên và có cả chế độ trực quan và dòng lệnh. | ex myfile |
| touch | Tạo một file nếu nó chưa tồn tại hoặc cập nhật timestamp nếu nó đã được tạo. | touch newfile |
| > | Tạo file bằng cách hướng đầu ra cho chúng. > tạo một file trong khi >> gắn với một file hiện có. | cal > calendar, ps > myprocs, date >> date.log
|




