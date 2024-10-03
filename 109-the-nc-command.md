# Lệnh `nc`

Lệnh `nc` (hoặc netcat) được sử dụng để thực hiện bất kỳ thao tác nào liên quan đến TCP (Transmission Control Protocol, giao thức kết nối), UDP (User Datagram Protocol, giao thức không kết nối, không đảm bảo việc truyền dữ liệu) hoặc UNIX-domain sockets. Nó có thể được coi là con dao đa năng cho các tiện ích giao thức truyền thông.

### Cú pháp:

```
nc [options] [ip] [port]
```

### Ví dụ:

#### 1. Mở kết nối TCP đến cổng 80 của máy chủ, sử dụng cổng 1337 làm cổng nguồn với thời gian chờ là 5 giây:

```bash
$ nc -p 1337 -w 5 host.ip 80
```

#### 2. Mở kết nối UDP đến cổng 80 trên máy chủ:

```bash
$ nc -u host.ip 80
```

#### 3. Tạo và lắng nghe trên UNIX-domain stream socket:

```bash
$ nc -lU /var/tmp/dsocket
```

#### 4. Tạo mô hình máy chủ/khách hàng cơ bản:

Điều này tạo ra một kết nối, không có phía máy chủ/khách hàng cụ thể đối với nc, một khi kết nối được thiết lập.

```bash
$ nc -l 1234 # trong một console

$ nc 127.0.0.1 1234 # trong một console khác
```

#### 5. Xây dựng mô hình truyền dữ liệu cơ bản:

Sau khi tệp đã được truyền, kết nối sẽ tự động đóng lại.

```bash
$ nc -l 1234 > filename.out # để bắt đầu lắng nghe trong một console và thu thập dữ liệu

$ nc host.ip 1234 < filename.in
```

#### 6. Giao tiếp với máy chủ:

Ví dụ cơ bản về việc truy xuất trang chủ của máy chủ, cùng với các tiêu đề.

```bash
$ printf "GET / HTTP/1.0\r\n\r\n" | nc host.ip 80
```

#### 7. Quét cổng:

Kiểm tra các cổng nào đang mở và chạy các dịch vụ trên các máy mục tiêu. Tham số `-z` ra lệnh để thông báo về những cổng đó thay vì khởi tạo một kết nối.

```bash
$ nc -zv host.ip 20-2000 # phạm vi các cổng để kiểm tra
```

### Các tham số và chức năng của chúng:

| **Tham số ngắn**    | **Mô tả**                                                          |
| -------------- | ----------------------------------------------------------------- |
| `-4`           | Buộc nc sử dụng địa chỉ IPv4                                      |
| `-6`           | Buộc nc sử dụng địa chỉ IPv6                                      |
| `-b`           | Cho phép phát sóng                                                |
| `-D`           | Bật chế độ gỡ lỗi trên socket                                     |
| `-i`           | Chỉ định khoảng thời gian trễ giữa các dòng gửi và nhận           |
| `-k`           | Tiếp tục lắng nghe cho kết nối khác sau khi kết nối hiện tại kết thúc |
| `-l`           | Lắng nghe kết nối đến thay vì khởi tạo một kết nối đến từ xa      |
| `-T`           | Chỉ định độ dài của TCP                                           |
| `-p`           | Chỉ định cổng nguồn được sử dụng                                  |
| `-r`           | Chỉ định cổng nguồn và/hoặc đích ngẫu nhiên                       |
| `-s`           | Chỉ định IP của giao diện được sử dụng để gửi các gói tin         |
| `-U`           | Sử dụng UNIX-domain sockets                                       |
| `-u`           | Sử dụng UDP thay vì TCP làm giao thức                             |
| `-w`           | Khai báo ngưỡng thời gian chờ cho các kết nối không hoạt động hoặc chưa thiết lập |
| `-x`           | Sử dụng giao thức được chỉ định khi nói chuyện với máy chủ proxy  |
| `-z`           | Chỉ định để quét các daemon đang lắng nghe, mà không gửi bất kỳ dữ liệu nào |