
# Lệnh `basename`

Lệnh `basename` là một tiện ích dòng lệnh loại bỏ thư mục khỏi tên tệp đã cho. Tùy chọn, nó cũng có thể loại bỏ bất kỳ hậu tố nào. Đây là một lệnh đơn giản chỉ chấp nhận một vài tùy chọn.

### Ví dụ

Ví dụ cơ bản nhất là in tên tệp với các thư mục dẫn đầu bị loại bỏ:

```bash
basename /etc/bar/foo.txt
```

Đầu ra sẽ bao gồm tên tệp:

```bash
foo.txt
```

Nếu bạn chạy basename trên một chuỗi đường dẫn trỏ đến một thư mục, bạn sẽ nhận được đoạn cuối cùng của đường dẫn. Trong ví dụ này, /etc/bar là một thư mục.

```bash
basename /etc/bar
```

Đầu ra

```bash
bar
```

Lệnh basename loại bỏ bất kỳ ký tự `/` nào ở cuối:

```bash
basename /etc/bar/foo.txt/
```

Đầu ra

```bash
foo.txt
```

### Tùy chọn

1. Theo mặc định, mỗi dòng đầu ra kết thúc bằng một ký tự xuống dòng. Để kết thúc các dòng bằng NUL, sử dụng tùy chọn -z (--zero).

```bash
$ basename -z /etc/bar/foo.txt
foo.txt$
```

2. Lệnh `basename` có thể chấp nhận nhiều tên làm đối số. Để làm như vậy, gọi lệnh với tùy chọn `-a` (`--multiple`), theo sau là danh sách các tệp được phân tách bằng dấu cách. Ví dụ, để lấy tên tệp của `/etc/bar/foo.txt` và `/etc/spam/eggs.docx` bạn sẽ chạy:

```bash
basename -a /etc/bar/foo.txt /etc/spam/eggs.docx
```

```bash
foo.txt
eggs.docx
```

### Cú pháp

The basename command supports two syntax formats:

```bash
basename NAME [SUFFIX]
basename OPTION... NAME...
```

### Các chức năng bổ sung

**Loại bỏ một hậu tố cuối**: Để loại bỏ bất kỳ hậu tố nào ở cuối tên tệp, hãy truyền hậu tố đó làm đối số thứ hai:

```bash
basename /etc/hostname name
host
```

Thông thường, tính năng này được sử dụng để loại bỏ phần mở rộng tệp

### Lệnh trợ giúp

Chạy lệnh sau để xem hướng dẫn đầy đủ về lệnh `basename`.

```bash
man basename
```
