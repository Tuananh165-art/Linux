# Lệnh `grep`

Bộ lọc `grep` tìm kiếm một tệp cho một mẫu ký tự cụ thể và hiển thị tất cả các dòng chứa mẫu đó.
grep là viết tắt của globally search for regular expression and print out. Mẫu được tìm kiếm trong tệp được gọi là biểu thức chính quy.

### Ví dụ:

1. Để tìm kiếm nội dung của tệp destination.txt cho một chuỗi ("KeY") không phân biệt chữ hoa chữ thường.

```
grep -i "KeY" destination.txt
```

2. Hiển thị số lượng kết quả khớp

```
grep -c "key" destination.txt
```

3. Chúng ta có thể tìm kiếm nhiều tệp và chỉ hiển thị các tệp chứa chuỗi/mẫu đã cho.

```
grep -l "key" destination1.txt destination2.txt destination3.xt destination4.txt
```

4. Để hiển thị số dòng của tệp với dòng khớp.

```
grep -n "key" destination.txt
```

5. Nếu bạn muốn grep các tệp nhật ký được giám sát, bạn có thể thêm `--line-buffered` để tìm kiếm chúng trong thời gian thực.

```
tail -f destination.txt | grep --line-buffered "key"
```

### Cú pháp:

The general syntax for the grep command is as follows:

```
grep [options] pattern [files]
```

### Các cờ bổ sung và chức năng của chúng:

| **Cờ ngắn**    | **Cờ dài**             | **Mô tả**                                                                                       |
| :------------- | :--------------------- | :---------------------------------------------------------------------------------------------- |
| `-c`           | `--count`              | in số lượng dòng khớp cho mỗi tệp đầu vào                                                       |
| `-h`           | `--no-filename`        | Hiển thị các dòng khớp, nhưng không hiển thị tên tệp                                            |
| `-i`           | `--ignore-case`        | Bỏ qua, không phân biệt chữ hoa chữ thường                                                      |
| `-l`           | `--files-with-matches` | Hiển thị danh sách chỉ các tên tệp.                                                             |
| `-n`           | `--line-number`        | Hiển thị các dòng khớp và số dòng của chúng.                                                    |
| `-v`           | `--invert-match`       | Điều này in ra tất cả các dòng không khớp với mẫu                                               |
| `-e`           | `--regexp=`            | Chỉ định biểu thức với tùy chọn này. Có thể sử dụng nhiều lần                                   |
| `-f`           | `--file=`              | Lấy các mẫu từ tệp, mỗi dòng một mẫu.                                                           |
| `-F`           | `--fixed-strings=`     | Diễn giải các mẫu như các chuỗi cố định, không phải biểu thức chính quy.                        |
| `-E`           | `--extended-regexp`    | Xử lý mẫu như một biểu thức chính quy mở rộng (ERE)                                             |
| `-w`           | `--word-regexp`        | Khớp toàn bộ từ                                                                                 |
| `-o`           | `--only-matching`      | Chỉ in các phần khớp của một dòng khớp, với mỗi phần như vậy trên một dòng đầu ra riêng biệt.   |
|                | `--line-buffered`      | Buộc đầu ra được đệm theo dòng.                                                                 |