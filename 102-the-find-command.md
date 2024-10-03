# Lệnh `find`

Lệnh `find` cho phép bạn **tìm kiếm các tệp trong một hệ thống thư mục**

-   Tìm kiếm tệp với tên cụ thể.
-   Tìm kiếm tệp với mẫu
-   Tìm kiếm các tệp và thư mục trống.


### Ví dụ:

1.  Tìm kiếm tệp với tên cụ thể:

```[linux]
find ./directory1 -name sample.txt
```

2. Tìm kiếm tệp với mẫu:

```[linux]
find ./directory1 -name '*.txt' 
```

3. Để tìm tất cả các thư mục có tên là test trong thư mục gốc.

```[linux]
find / -type d -name test
```

4. Tìm kiếm các tệp trống trong thư mục hiện tại

```[linux]
find . -size 0k
```

### Cú pháp:

```[linux]          
find [options] [paths] [expression]
```
**Nói một cách đơn giản** 
```[linux]
find [where to start searching from]
 [expression determines what to find] [-options] [what to find]
```

### Các tham số bổ sung và chức năng của chúng:

Các primaries thường được sử dụng bao gồm:
- `name` pattern - kiểm tra xem tên tệp có khớp với mẫu shell-glob đã cho hay không.
- `type` type - kiểm tra xem tệp có phải là loại đã cho hay không. Các loại tệp Unix được chấp nhận bao gồm:

| **Tuỳ chọn** |  **Mô tả**                                                                                           |
| :-------------  | :-------------------------------------------------------------------------------------------------------- |
| `b`           | thiết bị khối (đệm)                                                 |
| `d`            | thư mục                                                                      |
| `f`           | tệp thông thường |
| `l`             | Liên kết tượng trưng                                                                        |
| `-print`              | luôn trả về true; in tên của tệp hiện tại cộng với một dòng mới vào stdout.  |
| `-mtime n`              | tìm tất cả các tệp đã được sửa đổi n ngày trước. |
| `-atime n`              | tìm tất cả các tệp đã được truy cập 50 ngày trước. |
| `-cmin n` |              tìm tất cả các tệp đã được sửa đổi trong 1 giờ qua.|
| ` -newer file` |              tìm tệp đã được sửa đổi gần đây hơn tệp.|
| `-size n` |             Tệp sử dụng n đơn vị không gian, làm tròn lên.|

### Lệnh trợ giúp
Chạy lệnh dưới đây để xem hướng dẫn đầy đủ về lệnh `find` hoặc [nhấp vào đây](https://en.wikipedia.org/wiki/Find_(Unix)).
```[linux]
man find
```