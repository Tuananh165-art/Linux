# Lệnh `less`

Lệnh `less` là một trình phân trang terminal của Linux, hiển thị nội dung của tệp từng màn hình một. Hữu ích khi xử lý một tệp văn bản lớn vì nó không tải toàn bộ tệp mà truy cập từng trang một, dẫn đến tốc độ tải nhanh.

## Cú pháp
```
less [options] file_path
```

## Các tùy chọn
Một số tham số tùy chọn phổ biến bao gồm:
```
-E	less tự động thoát khi đến cuối tệp.
-f	Buộc less mở các tệp không phải tệp thông thường (thư mục hoặc tệp đặc biệt của thiết bị).
-F	Thoát less nếu toàn bộ tệp có thể được hiển thị trên màn hình đầu tiên.
-g	Tô sáng chuỗi cuối cùng được tìm thấy bằng cách tìm kiếm. Theo mặc định, less tô sáng tất cả các chuỗi khớp với lệnh tìm kiếm cuối cùng.
-G	Xóa tất cả các tô sáng từ các chuỗi được tìm thấy bằng cách tìm kiếm.
```
Để biết danh sách đầy đủ các tùy chọn, tham khảo tệp trợ giúp của less bằng cách chạy:
```
    less --help
```
## Một số ví dụ:
1. Mở một tệp văn bản
```
less /etc/updatedb.conf
```

2. Hiển thị số dòng
```
less -N /etc/init/mysql.conf
```

3. Mở tệp với tìm kiếm mẫu
```
less -pERROR /etc/init/mysql.conf
```
4. Loại bỏ nhiều dòng trống
```
less welcome.txt
```

Ở đây tôi đã chỉ cho bạn cách sử dụng lệnh less trong Linux. Mặc dù có các trình phân trang terminal khác, chẳng hạn như most và more, nhưng less có thể là một lựa chọn tốt hơn vì nó là một công cụ mạnh mẽ có mặt trong hầu hết mọi hệ thống.

Để biết thêm chi tiết: [Less Command in Linux](https://phoenixnap.com/kb/less-command-in-linux#:~:text=The%20less%20command%20is%20a,resulting%20in%20fast%20loading%20speeds.)
````
````
