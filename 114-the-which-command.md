# Lệnh `which`

Lệnh `which` xác định tệp thực thi nào sẽ được khởi chạy khi bạn đưa ra lệnh cho shell.
Nếu bạn có các phiên bản khác nhau của cùng một chương trình trên máy tính của mình, bạn có thể sử dụng which để tìm ra phiên bản nào shell sẽ sử dụng.

Nó có 3 trạng thái trả về như sau:

    0 : Nếu tất cả các lệnh được chỉ định đều được tìm thấy và có thể thực thi.
    1 : Nếu một hoặc nhiều lệnh được chỉ định không tồn tại hoặc không thể thực thi.
    2 : Nếu một tùy chọn không hợp lệ được chỉ định.

### Ví dụ

1. Để tìm đường dẫn đầy đủ của lệnh ls, hãy nhập lệnh sau:

```
which ls
```

2. Chúng ta có thể cung cấp nhiều hơn một đối số cho lệnh which:

```
which netcat uptime ping
```

Lệnh which tìm kiếm từ trái sang phải, và nếu có nhiều hơn một kết quả khớp được tìm thấy trong các thư mục được liệt kê trong biến đường dẫn PATH, which sẽ chỉ in ra kết quả đầu tiên.

3. Để hiển thị tất cả các đường dẫn cho lệnh được chỉ định:

```
which [filename] -a
```

4. Để hiển thị đường dẫn của các tệp thực thi node, hãy thực hiện lệnh:

```
which node
```

5. Để hiển thị đường dẫn của các tệp thực thi Java, hãy thực hiện:

```
which java  
```

### Cú pháp

```
which [filename1] [filename2] ...
```

Bạn có thể truyền nhiều chương trình và lệnh cho which, và nó sẽ kiểm tra chúng theo thứ tự.

Ví dụ:

```which ping cat uptime date head```

### Tùy chọn

-a : Liệt kê tất cả các phiên bản của tệp thực thi được tìm thấy (thay vì chỉ phiên bản đầu tiên của mỗi tệp).

-s : Không có đầu ra, chỉ trả về 0 nếu tất cả các tệp thực thi được tìm thấy, hoặc 1 nếu một số tệp không được tìm thấy.