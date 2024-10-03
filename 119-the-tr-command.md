# Lệnh `tr`

Lệnh `tr` trong UNIX là một tiện ích dòng lệnh để dịch hoặc xóa các ký tự.
Nó hỗ trợ một loạt các biến đổi bao gồm chuyển đổi chữ hoa thành chữ thường, nén các ký tự lặp lại, xóa các ký tự cụ thể và tìm kiếm và thay thế cơ bản.
Nó có thể được sử dụng với các ống UNIX để hỗ trợ dịch phức tạp hơn. `tr` là viết tắt của translate.

### Ví dụ:

1. Chuyển tất cả các chữ cái thường trong file1 thành chữ hoa.

```
$ cat file1
foo
bar
baz
tr a-z A-Z < file1
FOO
BAR
BAZ
```

2. Làm cho các dòng trống liên tiếp thành một.

```
$ cat file1
foo


bar


baz
$ tr -s "\n" < file1
foo
bar
baz
```

3. Xóa mã dòng mới.

```
$ cat file1
foo
bar
baz
$ tr -d "\n" < file1
foobarbaz%
```

### Cú pháp:

Cú pháp chung cho lệnh `tr` như sau:

```
tr [options] string1 [string2]
```

### Các tham số bổ sung và chức năng của chúng:

| **Tham số ngắn**    | **Tham số dài**    | **Mô tả**                                                                                                     |
| :------------- | :------------ | :------------------------------------------------------------------------------------------------------------ |
| `-C`           |               | Bổ sung tập hợp các ký tự trong string1, tức là `-C ab` bao gồm mọi ký tự ngoại trừ `a` và `b`.               |
| `-c`           |               | Giống như -C.                                                                                                 |
| `-d`           |               | Xóa các ký tự trong string1 khỏi đầu vào.                                                                     |
| `-s`           |               | Nếu có một chuỗi các ký tự trong string1, kết hợp chúng thành một.                                            |