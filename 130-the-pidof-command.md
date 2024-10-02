# Lệnh `pidof`

Lệnh `pidof` là một tiện ích dòng lệnh cho phép bạn tìm ID tiến trình của một chương trình đang chạy.

## Cú pháp
````

pidof [OPTIONS] PROGRAM_NAME
````

Để xem thông báo trợ giúp và tất cả các tùy chọn của lệnh:
````

[user@home ~]$ pidof -h

 -c           Trả về các PID có cùng thư mục gốc
 -d <sep>     Sử dụng ký tự được cung cấp làm dấu phân cách đầu ra
 -h           Hiển thị văn bản trợ giúp này
 -n           Tránh sử dụng hàm hệ thống stat trên các chia sẻ mạng
 -o <pid>     Bỏ qua các kết quả với PID được chỉ định
 -q           Chế độ yên lặng. Không hiển thị đầu ra
 -s           Chỉ trả về một PID
 -x           Trả về các PID của các shell đang chạy các tập lệnh có tên khớp
 -z           Liệt kê các tiến trình zombie và I/O đang chờ. Có thể khiến pidof bị treo.
````

## Ví dụ:
Để tìm PID của máy chủ SSH, bạn sẽ chạy:

````

pidof sshd
````

Nếu có các tiến trình đang chạy với tên khớp với `sshd`, các PID của chúng sẽ được hiển thị trên màn hình. Nếu không tìm thấy kết quả nào, đầu ra sẽ trống.

````

# Đầu ra
4382 4368 811
````

`pidof` trả về `0` khi ít nhất một chương trình đang chạy khớp với tên được yêu cầu. Nếu không, mã thoát là `1`. Điều này có thể hữu ích khi viết các tập lệnh shell.

Để đảm bảo rằng chỉ các PID của chương trình bạn đang tìm kiếm được hiển thị, hãy sử dụng đường dẫn đầy đủ đến chương trình làm đối số. Ví dụ, nếu bạn có hai chương trình đang chạy với cùng tên nằm trong hai thư mục khác nhau, pidof sẽ hiển thị PID của cả hai chương trình đang chạy.

Theo mặc định, tất cả các PID của các chương trình đang chạy khớp sẽ được hiển thị. Sử dụng tùy chọn `-s` để buộc pidof chỉ hiển thị một PID:

````

pidof -s program_name
````

Tùy chọn `-o` cho phép bạn loại trừ một tiến trình với một PID nhất định khỏi đầu ra của lệnh:

````

pidof -o pid program_name
````

Khi pidof được gọi với tùy chọn `-o`, bạn có thể sử dụng một PID đặc biệt có tên %PPID đại diện cho shell hoặc tập lệnh shell đang gọi.

Để chỉ trả về các PID của các tiến trình đang chạy với cùng thư mục gốc, sử dụng tùy chọn `-c`.
Tùy chọn này chỉ hoạt động khi pidof được chạy với quyền `root` hoặc `sudo`:

````

pidof -c pid program_name
````

## Kết luận

Lệnh `pidof` được sử dụng để tìm ra các PID của một chương trình đang chạy cụ thể.

`pidof` là một lệnh đơn giản không có nhiều tùy chọn. Thông thường bạn sẽ gọi pidof chỉ với tên của chương trình bạn đang tìm kiếm.
````
````
