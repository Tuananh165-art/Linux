# Lệnh `wc`

Lệnh `wc` là viết tắt của word count. Nó được sử dụng để đếm số dòng, từ và byte *(ký tự)* trong một tệp hoặc đầu vào tiêu chuẩn sau đó in kết quả ra đầu ra tiêu chuẩn.

### Ví dụ:

1. Để đếm số dòng, từ và ký tự trong một tệp theo thứ tự:

```
wc file.txt
```

2. Để đếm số thư mục trong một thư mục:

```
ls -F | grep / | wc -l
```

### Cú pháp:

```bash
wc [OPTION]... [FILE]...
```

### Các cờ bổ sung và chức năng của chúng:

|**Cờ ngắn**   |**Cờ dài**   |**Mô tả**   |
|:---|:---|:---|
|`-c` | `--bytes` | in số byte|
|`-m` | `--chars` | in số ký tự|
|`-l` | `--lines` | in số dòng mới|
|<center>-</center> | `--files0-from=F` | đọc đầu vào từ các tệp được chỉ định bởi tên kết thúc bằng NUL trong tệp F. Nếu F là `-` thì đọc tên từ đầu vào tiêu chuẩn|
|`-L` | `--max-line-length` | in chiều rộng hiển thị tối đa|
|`-w` | `--words` | in số từ|

### Ghi chú bổ sung:

* Truyền nhiều hơn một tệp cho lệnh `wc` sẽ in số lượng cho mỗi tệp và tổng số của chúng.
* bạn có thể kết hợp nhiều cờ để in kết quả như bạn muốn.