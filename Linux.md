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
| > | Tạo file bằng cách hướng đầu ra cho chúng. > tạo một file trong khi >> gắn với một file hiện có. | cal > calendar, ps > myprocs, date >> date.log |

Thông thường bạn phải xem xét nội dung của nhiều file khác nhau. Việc rà soát các file khác nhau thường xuyên thường khá phức tạp và tốn nhiều thời gian. Do đó cách đơn giản nhất để đọc nội dung của chúng là sử dụng câu lệnh cat. Cú pháp câu lệnh khá đơn giản:

`cat FILENAME` 

Linux cung cấp một số lệnh để xem xét nội dung và bản chất của các file. Sau đây là một số lệnh hữu ích nhất.

| Lệnh | Chức năng | Ví dụ | 
|------|-----------|-------|
| cat | Hiển thị toàn bộ nội dung của một file văn bản.	| 	cat .bashrc |
| more | Hiển thị nội dung của file văn bản. Nhấn phím cách để di chuyển đến từng đoạn bổ sung.	| more .bash_history |
| less Hiển thị nội dung của file văn bản, nhưng cho phép quay trở lại bằng phím mũi tên lên trên. | less .bash_history |
| file | 	Xác định các file theo loại (ví dụ: văn bản ASCII, file thực thi, hình ảnh, thư mục) | file myfile, file ~/.bashrc, file /bin/echo |

### Sao chép hoặc di chuyển file

Việc sao chép hoặc di chuyển file trong Linux terminal khá đơn giản và dễ dàng.

Để sao chép một file, bạn có thể sử dụng lệnh: cp.
Để di chuyển 1 file bạn sử dụng câu lệnh: `mvoflder.`
Cả 2 lệnh sử dụng khá đơn giản. Với lệnh cp. Để sao chép một file, bạn nhập tên file và nhập tên file copy mới. Ví dụ:

`cp file1 file2`
Trên câu lệnh trên sao chép file1 và tạo ra file2 có chứa nội dụng file1. Bạn có thể sử dụng cp để sao chép thư mục. Điều quan trọng cần lưu ý khi muốn sao chép một thư mục bạn nên sử dụng tùy chọn -r.

Nói cách khác, cp -r sẽ sao chép nội dung của một thư mục nhất định (và các thư mục con) sang thư mục bạn lựa chọn. Ngoài ra bạn có thể sử dụng cp với đường dẫn đầy đủ:

`cp -r /home/marin/work/ /home/marin/backup`
Câu lệnh trên sẽ sao chép nội dung của thư mục "work" sang thư mục mới có tên "backup".

Nếu muốn sao chép tất cả các file và thư mục của một thư mục sang một thư mục khác, bạn có thể sử dụng ký tự "*". Ký tự được sử dụng để tìm các cổng phù hợp (trường hợp này là các file và thư mục). Ví dụ:

`cp /home/marin/work/* /home/marin/backup/`

Tiếp theo là lệnh mv. Cú pháp câu lệnh:

`mv file1 file2`
Câu lệnh trên đổi tiên file1 thành file2. Tương tự với thư mục cũng thế. Tuy nhiên nếu bạn chỉ định 1 file và 1 thư mục, file sẽ được di chuyển vào trong thư mục. Chẳng hạn:

`mv /home/marin/file1 /home/marin/work/`

Trong câu lệnh trên sẽ di chuyển file1 từ “`/home/marin/” sang “/home/marin/work/`”. Nếu bạn muốn di chuyển tất cả các file trong một thư mục sang thư mục khác, bạn có thể sử dụng ký tự `"*"`:

`mv /home/marin/work/* /home/marin/backup/`
 












