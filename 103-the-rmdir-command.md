# Lệnh `rmdir`

Lệnh **rmdir** được sử dụng để xóa các thư mục trống khỏi hệ thống tệp trong Linux. Lệnh rmdir xóa từng thư mục được chỉ định trong dòng lệnh chỉ khi các thư mục này trống.

### Cách sử dụng và Ví dụ:

1. xóa thư mục và các thư mục cha của nó
```
rmdir -p a/b/c			// tương tự như 'rmdir a/b/c a/b a'
```
2. xóa nhiều thư mục
```
rmdir a b c				// xóa các thư mục trống a, b và c
```

### Cú pháp:

```
rmdir [OPTION]... DIRECTORY...
```

### Các tham số bổ sung và chức năng của chúng:

|**Tham số ngắn**   |**Tham số dài**   |**Mô tả**   |
|:---|:---|:---|
|`-`|`--ignore-fail-on-non-empty`|bỏ qua mỗi lỗi chỉ vì một thư mục không trống|
|`-p`|`--parents`|xóa DIRECTORY và các thư mục cha của nó|
|`-d`|`--delimiter=DELIM`|sử dụng DELIM thay vì TAB cho dấu phân cách trường|
|`-v`|`--verbose`|xuất một chẩn đoán cho mỗi thư mục được xử lý|