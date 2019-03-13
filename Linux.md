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

* Để sao chép một file, bạn có thể sử dụng lệnh: cp.
* Để di chuyển 1 file bạn sử dụng câu lệnh: `mvoflder.`
* Cả 2 lệnh sử dụng khá đơn giản. Với lệnh cp. Để sao chép một file, bạn nhập tên file và nhập tên file copy mới. Ví dụ:

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
 

### Xóa các file và thư mục


Nếu muốn xóa một thư mục hoặc một file bạn có thể sử dụng lệnh rm. Điều quan trọng bạn cần lưu ý là khi sử dụng lệnh này để xóa một file hoặc thư mục, các file này không thể restore được. Để xóa 1 file bạn thực hiện:

`rm /home/marin/useless-file.txt`
Bạn có thể sử dụng rm với nhiều tùy chọn khác nhau. Một số tùy chọn quan trọng như:

* -f: buộc xóa các file có thông báo nhắc nhở
* -i: nhắc nhở trước khi xóa
* -r: xóa bỏ các thư mục đệ quy
* -d: xóa các thư mục rỗng
* -v: giải thích đang thực hiện nhiệm vụ gì

### Tìm file

Có hai lệnh có thể giúp người dùng tìm file trên Linux, nhưng chúng hoạt động rất khác nhau. Một lệnh tìm kiếm hệ thống file, còn lệnh kia xem xét cơ sở dữ liệu được xây dựng trước đó.
| Lệnh | Chức năng | Ví dụ |
|------|-----------|-------|
| find | Định vị các file dựa trên các tiêu chí được cung cấp (tên, loại, chủ sở hữu, quyền, kích thước file, v.v...). Trừ khi được cung cấp một vị trí để bắt đầu tìm kiếm, còn nếu không lệnh này chỉ tìm trong thư mục hiện hành. | find . -name myfile, find /tmp -type d |
| locate | Định vị các file bằng cách sử dụng nội dung của /var/lib/mlocate/mlocate.db được cập nhật bằng lệnh updateb chạy qua cron. Không yêu cầu vị trí bắt đầu. | locate somefile  |


### Hiển thị tiến trình trong hệ thống Linux

Một trong những công việc cần thiết khi quản trị hệ thống Linux đó là kiểm soát các tiến trình hiện đang chạy. Khi đã biết được những tiến trình nào đang chạy bạn có thể tắt những tiến trình gây giảm tốc độ của hệ thống. Ngoài ra, thông tin về những tiến trình hệ thống cho chúng ta biết nên tắt nhưng tiến trình làm cho hệ thống vận hành không ổn định. Do đó việc biết được những tiến trình nào đang chạy trên hệ thống rất quan trọng. Linux hỗ trợ nhiều phương pháp kiểm tra tiến trình, một trong số đó là sử dụng lệnh `ps`. Khi sử dụng lệnh này mọi thông tin về những tiến trình đang chạy sẽ được hiển thị. Bạn chỉ cần nhập cú pháp lệnh sau vào cửa sổ terminal



<img src="/img/01.JPG">

* `ps –A`: Kiểm tra mọi tiến trình trong hệ thống.
* `ps -U root -u root –N`: Kiểm tra mọi tiến trình ngoại trừ những tiến trình hệ thống.
* `ps -u username`: Kiểm tra những tiến trình được thực hiện bởi một người dùng nhất định.

Hoặc bạn có thể sử dụng lệnh  `top` để xem những tiến trình đang chạy trên hệ thống trong thời gian thực.

### Kiểm tra thông tin Socket và thông tin mạng TCP/UDP 

Kiểm tra thông tin Socket và thông tin mạng TCP/UDP.

Sau khi cấu hình những dịch vụ mạng của hệ thống Linux, bạn cần phải giữ lại tab của các cổng đang thực sự nhận tín hiệu trên giao diện mạng của hệ thống. Điều này rất quan trọng vì hệ thống có thể bị xâm nhập qua các cổng mở. Có một số công cụ quản lý Linux thông báo cho bạn biết thông tin của những cổng mởvà truy cập vào những cổng đang mở trên mạng. Một trong những phương pháp đơn giản và tin cậy nhất đó là sử dụng lệnh ss để kiểm tra thông tin Socket, ngoài ra lệnh này còn có thể hiển thị nhiều thông tin TCP và thông tin trạng thái hơn các công cụ khác. Lệnh ss này cung cấp thông tin về:

* Mọi Socket TCP.
* Mọi Socket UDP.
* Mọi kết nối ssh/ftp/http/https.
* Mọi tiến trình cục bộ được kết nối tới máy chủ X.
* Mọi Socket TCP trong trạng thái FIN-WAIT-1.
* Dưới đây là một số lệnh ss:

<img src="/img/02.JPG">

* `ss -1`: Hiển thị mọi cổng mở.

<img src="/img/03.JPG">

* ss –pl: Kiểm tra tên tiến trình sử dụng Socket mở sử dụng lệnh sau:
* ss -lp | grep: Kiểm tra người dùng đang làm việc với Socket mở.
* ss -t –a: Hiển thị mọi Socket TCP.
* ss -u –a: Hiển thị mọi Socket UDP.

### Theo dõi Average CPU Load và Disk Activity

`yum install sysstat -y`

Nếu là một quản trị viên hệ thống Linux, bạn cần phải biết phương pháp duy trì một sự cân bằng hợp lý trong quá trình tải đầu vào và đầu ra giữa các ổ đĩa vật lý. Bạn có thể thay đổi cấu hình hệ thống để thực hiện tác vụ này. Tuy nhiên có một phương pháp đơn giản hơn rất nhiều đó là sử dụng lệnh isostat để quản lý hệ thống thiết bị tải đầu vào và đầu ra trong Linux bằng cách theo dõi thời gian hoạt động và tốc độ truyền trung bình của những thiết bị này. Lệnh này sẽ thông báo thông tin của CPU (Central Processing Unit), thông tin đầu vào và đầu ra cho những thiết bị, phân vùng và hệ thống file mạng (NFS).

Khi chạy lệnh isostat thông tin kết xuất có dạng:

Để lấy thông tin thư mục NFS bạn hãy sử dụng lệnh sau:

`iostat –n`

<img src="/img/04.JPG">

 ### Kiểm tra Memory Map của các tiến trình trong Linux
 
 `free -m`
 
 ### Kiểm tra thời gian vận hành của hệ thống
 
 Bạn có muốn biết máy chủ đã vận hành bao lâu? Nếu muốn bạn chỉ cần sử dụng lênh uptime để kiểm tra thời gian mà hệ thống đã vận hành. Lệnh đơn giản này không chỉ cho bạn biết thời gian hệ thống vận hành mà còn cho biết lượng người dùng đã đăng nhập vào hệ thống trong một khoảng thời gian trước đó.
 
 `uptime`
 
 ```
 [root@controller ~]# uptime
 02:44:18 up  4:50,  1 user,  load average: 0.09, 0.06, 0.05
[root@controller ~]#
```
### Kiểm tra người dùng đăng nhập

Ngoài những công cụ quản lý Linux, bạn có thể sử dụng một lệnh để kiểm tra những người dùng nào đã thực hiên đăng nhập vào hệ thống và những gì họ đã thực hiện. Lệnh này sẽ hiển thị thời gian hiện tại, thời gian hệ thống đã vận hành, lượng người dùng đã đăng nhập.

Ngoài ra lệnh này cũng hiển thị lượng tải trung bình trong mỗi 1, 5 và 15 phút. Lệnh này rất hữu dụng với những Admin hệ thống muốn sử dụng thông tin tải trung bình để hoạch định dung lượng.

Để kiểm tra ai đã đăng nhập vào hệ thống và những tác vụ họ đã thực hiện bạn chỉ cần chạy lệnh sau:

` w username`
### Kiểm soát hành vi hệ thống, phần cứng và thông tin hệ thống trong Linux

Với nhiều người dùng Linux, kiểm soát hệ thống là một tác vụ phức tạp. Hầu hết các bản phân phối Linux tích hợp khá nhiều công cụ kiểm soát. Những công cụ kiểm soát này cung cấp các phương pháp có thể được áp dụng để kiểm tra thông tin hành vi hệ thống. Việc kiểm soát hệ thống cho phép người dùng theo dõi nguyên nhân khả năng thực thi của hệ thống bị cản trở. Một trong những tác vụ cần thiết của quá trình kiểm soát hệ thống là tra cứu thông tin về hành vi hệ thống, phần cứng và thông tin bộ nhớ. Có một lệnh đơn giản giúp hiển thị thông tin về tiến trình, bộ nhớ, trang ghi, nhóm IO, lỗi và hành vi CPU đó là lệnh vmstat.

Bạn chỉ cần nhập lệnh sau vào cửa sổ terminal:

` vmstat 3`

```
[root@controller ~]# vmstat 3
procs -----------memory---------- ---swap-- -----io---- -system-- ------cpu-----
 r  b   swpd   free   buff  cache   si   so    bi    bo   in   cs us sy id wa st
 1  0      0 7194328   2232 391808    0    0     4    20   67   66  0  0 100  0  0
 0  0      0 7194212   2232 391808    0    0     0     3  248  225  0  0 100  0  0
 0  0      0 7194212   2232 391808    0    0     0   143  281  280  0  0 100  0  0
```
Ngoài ra bạn có thể sử dụng lệnh `vmstat –m` để kiểm tra thông tin bộ nhớ, và lệnh `vmstat –a` để hiển thị thông tin trang nhớ đang hoạt động và không hoạt động.


```
[root@controller ~]# vmstat -a
procs -----------memory---------- ---swap-- -----io---- -system-- ------cpu-----
 r  b   swpd   free  inact active   si   so    bi    bo   in   cs us sy id wa st
 1  0      0 7194460 161116 440660    0    0     4    20   67   66  0  0 100  0  0
[root@controller ~]#
```

### Bắt đầu, dừng và liệt kê các service

| Lệnh | Chức năng | Ví dụ | 
|------|-----------|-------|
|systemctl | Lệnh systemctl có thể bắt đầu, dừng, khởi động lại và load lại các service, cần có quyền admin.	|systemctl stop apache2.service, systemctl restart apache2.service |
| service | Liệt kê các service và cho biết liệu chúng có đang chạy không.	| service --status-all |

### Xác định phiên bản hệ điều hành

Bảng bên dưới liệt kê các lệnh sẽ hiển thị chi tiết về hệ điều hành Linux đang chạy trên hệ thống.

| Lệnh | Chức năng | Ví dụ |
|------|-----------|-------|
| uname | Hiển thị thông tin về phiên bản hệ điều hành trong một dòng văn bản.	 | uname -a, uname -r|
| lsb_release | Trên các hệ thống dựa trên Debian, lệnh này hiển thị thông tin về hệ điều hành bao gồm codename và ID nhà phân phối.	 | lsb_release -a |
| hostnamectl | Hiển thị thông tin trên hệ thống bao gồm tên máy chủ, loại chassis (thùng máy), hệ điều hành, kernel và cấu trúc.	 | hostnamectl |

### Đo hiệu suất hệ thống

Sau đây là một số công cụ hữu ích để kiểm tra hiệu năng hệ thống.


| Lệnh | Chức năng | Ví dụ |
|------|-----------|-------|
| top | Hiển thị các tiến trình đang chạy cùng với việc sử dụng tài nguyên và dữ liệu hiệu suất hệ thống. Có thể hiển thị các tiến trình cho một người dùng đã chọn hoặc tất cả người dùng. Các tiến trình có thể được sắp xếp theo các tiêu chí khác nhau (theo mặc định là mức độ sử dụng CPU). | top |
| atop | Tương tự như lệnh trên nhưng hướng nhiều đến hiệu năng hệ thống hơn so với các tiến trình riêng lẻ.	| atop |
| free | Hiển thị bộ nhớ và trao đổi tổng bộ nhớ, phần đã sử dụng và còn trống.	| free |
| df | Hiển thị việc sử dụng không gian ổ đĩa hệ thống của file.	 | df |

### Quản lý người dùng và nhóm

Các lệnh để tạo và xóa tài khoản người dùng và các nhóm khá đơn giản.

| Lệnh | Chức năng | Ví dụ |
|------|-----------|-------|
| useradd | Thêm tài khoản người dùng mới vào hệ thống. Tên người dùng là bắt buộc. Các trường khác (mô tả người dùng, shell, mật khẩu ban đầu, v.v...) có thể được chỉ định. Thư mục chính sẽ mặc định là /home/username.	 | useradd -c "John Doe" jdoe \
| userdel | Xóa tài khoản người dùng khỏi hệ thống. Tùy chọn -f mạnh mẽ hơn, xóa các file chính và file người dùng khác ngay cả khi người dùng vẫn đăng nhập.	| userdel -f jbdoe |
| groupadd | Thêm một nhóm người dùng mới vào hệ thống, cập nhật /etc/group. | groupadd developers |
| groupdel | Xóa nhóm người dùng khỏi hệ thống.	| groupdel developers |


### Thiết lập và chạy các tiến trình theo lịch
	
Các tác vụ có thể được lên lịch để chạy định kỳ bằng cách sử dụng lệnh được liệt kê dưới đây.

| Lệnh | Chức năng | Ví dụ |
|------|-----------|-------|
| crontab | Thiết lập và quản lý các tiến trình theo lịch. Với tùy chọn -l, các công việc định kỳ được liệt kê. Với tùy chọn -e, các công việc định kỳ có thể được thiết lập để chạy ở các khoảng thời gian đã chọn.	| crontab -e, crontab -l -u username|
| ancrontab | Cho phép người dùng chỉ chạy các công việc theo lịch trình hàng ngày. Nếu hệ thống bị tắt khi một công việc được đặt lịch chạy, nó sẽ chạy khi hệ thống khởi động.	| vi /etc/anacrontab |

### Cập nhật, cài đặt và liệt kê các ứng dụng

Các lệnh để cài đặt và cập nhật ứng dụng tùy thuộc vào phiên bản Linux đang sử dụng, cụ thể là dựa trên nền tảng Debian hay RPM.

| Lệnh |	Chức năng |	Ví dụ |
|------|-----------|-------|
| apt update |	Trên các hệ thống dựa trên Debian, lệnh này cập nhật danh sách các gói có sẵn và các phiên bản của chúng, nhưng không cài đặt hoặc nâng cấp bất kỳ gói nào |	sudo apt update |
| apt upgrade |	Trên các hệ thống dựa trên Debian, lệnh này cài đặt các phiên bản mới hơn của các gói đã có. |	sudo apt upgrade |
| apt list	| Liệt kê tất cả các gói được cài đặt trên hệ thống dựa trên Debian. Với tùy chọn --upgradable, nó chỉ hiển thị các gói có bản nâng cấp.|	apt list
apt list --installed
apt list --upgradable|
| apt install |	Trên các hệ thống dựa trên Debian, lệnh này cài đặt gói được yêu cầu.	| sudo apt install apache2 |
| yum update |	Trên các hệ thống dựa trên RPM, lệnh này cập nhật tất cả hoặc các gói được chỉ định.|	sudo yum update
yum update mysql|
| yum list |	Trên các hệ thống dựa trên RPM, lệnh này liệt kê các gói.	| sudo yum update mysql |
| yum install |	Trên các hệ thống dựa trên RPM, lệnh này cài đặt gói được yêu cầu.	| sudo yum -y install firefox|
| yum list	| Trên các hệ thống dựa trên RPM, lệnh này liệt kê các gói đã biết và đã cài đặt.|	sudo yum list
sudo yum list --installed|


### Tắt và khởi động lại

Các lệnh tắt và khởi động lại hệ thống Linux yêu cầu quyền admin. Các tùy chọn như +15 là số phút mà lệnh sẽ đợi trước khi yêu cầu tắt máy được thực hiện.

| Lệnh |	Chức năng |	Ví dụ |
|------|-----------|-------|
| shutdown	| Tắt hệ thống tại thời điểm yêu cầu. Tùy chọn -H tạm dừng hệ thống, còn tùy chọn -P sẽ tắt nguồn.|	sudo shutdown -H now, shutdown -H +15, shutdown -P +5|
| halt |	Tắt hệ thống tại thời điểm yêu cầu. |	sudo halt, sudo halt -p,sudo halt --reboot|
| poweroff	| Ngắt nguồn khỏi hệ thống tại thời điểm yêu cầu.	| sudo shutdown -H now ,sudo shutdown -H +15, sudo shutdown -P +5 |


