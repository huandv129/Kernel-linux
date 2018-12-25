Một ngày đẹp trời toàn bộ server của hệ thống bị nâng Kernel. Giờ chỉ cần Reboot là service kia không chạy nữa. 

Với Grub ta vẫn có phần Advanded để chọn Kernel cũ khi boot.

<img src="/img/1.png"

Nhưng với hàng trăm server thì lại phải chờ nó khởi động rồi vào chọn hay sao. 
Search một lúc thì mình thấy là có thể cấu hình grub để nó làm việc này thay cho mình.

Bây giờ ta muốn Server của ta luôn luôn boot bằng `kernel 4.4.0-59`. Đơn giản ta chỉ việc vào `file /etc/default/grub` tìm dòng `GRUB_DEFAULT=0` và sửa thành


``` sh
GRUB_DEFAULT="Advanced options for Ubuntu>Ubuntu, with Linux 4.4.0-59-generic"  
```
Như đoạn trên ta có thể `Grub` sẽ vào `Advanced options for Ubuntu` và tiếp theo là `Ubuntu, with Linux 4.4.0-59-generic`

Lưu lại và chạy lệnh cập nhật grub `update-grub`

``` sh
root@test:~# update-grub  
Generating grub configuration file ...  
Found linux image: /boot/vmlinuz-4.4.0-62-generic  
Found initrd image: /boot/initrd.img-4.4.0-62-generic  
Found linux image: /boot/vmlinuz-4.4.0-59-generic  
Found initrd image: /boot/initrd.img-4.4.0-59-generic  
Found linux image: /boot/vmlinuz-4.4.0-31-generic  
Found initrd image: /boot/initrd.img-4.4.0-31-generic  
done  
```
Reboot lại server và kiểm tra.






