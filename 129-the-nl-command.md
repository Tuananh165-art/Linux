# Lệnh `nl`

Lệnh “nl” đánh số các dòng trong một tệp. Một cách khác để xem nội dung của một tệp, lệnh “nl” có thể rất hữu ích cho nhiều tác vụ.
## Cú pháp
```
nl [ -b Type ] [ -f Type ] [ -h Type ] [ -l Number ] [ -d Delimiter ] [ -i Number ] [ -n Format ] [ -v Number ] [ -w Number ] [ -p ] [ -s Separator ] [ File ]
```
## Ví dụ:
1. Để đánh số tất cả các dòng:
```
nl  -ba  chap1
```

2. Hiển thị tất cả các dòng văn bản:
```
[server@ssh ~]$ nl states
1 Alabama
2 Alaska
3 Arizona
4 Arkansas
5 California
6 Colorado
7 Connecticut.
8 Delaware
```

3. Chỉ định định dạng số dòng khác
```
nl  -i10  -nrz  -s::  -v10  -w4  chap1
```

Bạn chỉ có thể đặt tên một tệp trên dòng lệnh. Bạn có thể liệt kê các tham số và tên tệp theo bất kỳ thứ tự nào.