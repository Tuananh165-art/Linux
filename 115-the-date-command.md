# Lệnh `date`

Lệnh `date` được sử dụng để in ngày và giờ hiện tại của hệ thống.

Lệnh `date` cũng được sử dụng để đặt ngày và giờ của hệ thống, nhưng bạn cần phải là siêu người dùng *(root)* để làm điều đó.

### Ví dụ:

1. Để hiển thị ngày và giờ hiện tại:

```
date
```

2. Bạn có thể sử dụng tùy chọn -u để hiển thị ngày và giờ theo múi giờ UTC *(Coordinated Universal Time)*

```
date -u
```

1. Để hiển thị bất kỳ chuỗi ngày nào đã cho dưới dạng ngày định dạng:

```
date --date="2/02/2010"
date --date="2 years ago"
```

### Cú pháp:

```
date [OPTION]... [+FORMAT]
date [-u|--utc|--universal] [MMDDhhmm[[CC]YY][.ss]]
```

### Các tham số bổ sung và chức năng của chúng:

|**Tham số ngắn**   |**Tham số dài**   |**Mô tả**   |
|:---|:---|:---|
|`-d`|`--date=STRING`|chuyển đổi chuỗi đã cung cấp thành ngày định dạng|
|`-f`|`--file=DATEFILE`|giống như `--date` nhưng cho các tệp|
|`-I[FMT]`|`--iso-8601[=FMT]`|Hiển thị ngày và giờ theo định dạng ISO 8601|
|`-r`|`--reference=FILE`|Hiển thị thời gian sửa đổi cuối cùng của FILE|
|`-s`|`--set=STRING`|đặt thời gian thành thời gian được mô tả bởi STRING|
|`-u`|`--universal`|hiển thị ngày và giờ theo múi giờ UTC *(Coordinated Universal Time)*|
|`-R`|`--rfc-email`|Hiển thị ngày và giờ theo định dạng ISO 8601 Ví dụ: (Fri, 22 Oct 2021 05:18:42 +0200)|
|<center>-<center>|`rfc-3339=FMT`|Hiển thị ngày và giờ theo định dạng RFC 3339|
|<center>-<center>|`--debug`|Thường được sử dụng với `--date` để chú thích ngày đã phân tích và cảnh báo về việc sử dụng đáng ngờ tới stderr|

### Kiểm soát đầu ra:

Bạn có thể sử dụng các định dạng định dạng để kiểm soát ngày và giờ đầu ra.

### Ví dụ:
|**Lệnh**   |**Đầu ra**   |
|:---|:---|
|`$ date "+%D"`|`10/22/21`|
|`$ date "+%D %T"`|`10/22/21 05:33:51`|
|`$ date "+%A %B %d %T %y"`|`Friday October 22 05:34:47 21`|

### Cú pháp:

```
date "+%[format-options ...]"
```

### Danh sách các định dạng định dạng để kiểm soát đầu ra:

|**Định dạng**   |**Mô tả**   |
|:---|:---|
|`%a`|tên viết tắt của ngày trong tuần *(ví dụ: Sun)*|
|`%A`|tên đầy đủ của ngày trong tuần *(ví dụ: Sunday)*|
|`%b`|tên viết tắt của tháng *(ví dụ: Jan)*|
|`%B`|tên đầy đủ của tháng *(ví dụ: January)*|
|`%c`|ngày và giờ *(ví dụ: Thu Mar  3 23:05:25 2005)*|
|`%C`|thế kỷ; giống như %Y, ngoại trừ bỏ qua hai chữ số cuối (ví dụ: 20)|
|`%d`|ngày trong tháng (ví dụ: 01)|
|`%D`|ngày; giống như %m/%d/%y|
|`%e`|ngày trong tháng, có khoảng trắng; giống như %_d|
|`%F`|ngày đầy đủ; giống như %Y-%m-%d|
|`%g`|hai chữ số cuối của năm của số tuần ISO (xem %G)|
|`%G`|năm của số tuần ISO (xem %V); thường chỉ hữu ích với %V|
|`%h`|giống như %b|
|`%H`|giờ (00..23)|
|`%I`|giờ (01..12)|
|`%j`|ngày trong năm (001..366)|
|`%k`|giờ, có khoảng trắng ( 0..23); giống như %_H|
|`%l`|giờ, có khoảng trắng ( 1..12); giống như %_I|
|`%m`|tháng (01..12)|
|`%M`|phút (00..59)|
|`%n`|một dòng mới|
|`%N`|nano giây (000000000..999999999)|
|`%p`|tương đương với AM hoặc PM của địa phương; để trống nếu không biết|
|`%P`|giống như %p, nhưng viết thường|
|`%q`|quý của năm (1..4)|
|`%r`|thời gian đồng hồ 12 giờ của địa phương (ví dụ: 11:11:04 PM)|
|`%R`|giờ và phút 24 giờ; giống như %H:%M|
|`%s`|giây kể từ 1970-01-01 00:00:00 UTC|
|`%S`|giây (00..60)|
|`%t`|một tab|
|`%T`|thời gian; giống như %H:%M:%S|
|`%u`|ngày trong tuần (1..7); 1 là Thứ Hai|
|`%U`|số tuần của năm, với Chủ Nhật là ngày đầu tiên của tuần (00..53)|
|`%V`|số tuần ISO, với Thứ Hai là ngày đầu tiên của tuần (01..53)|
|`%w`|ngày trong tuần (0..6); 0 là Chủ Nhật|
|`%W`|số tuần của năm, với Thứ Hai là ngày đầu tiên của tuần (00..53)|
|`%x`|đại diện ngày của địa phương (ví dụ: 12/31/99)|
|`%X`|đại diện thời gian của địa phương (ví dụ: 23:13:48)|
|`%y`|hai chữ số cuối của năm (00..99)|
|`%Y`|năm|
|`%z`|múi giờ số +hhmm (ví dụ: -0400)|
|`%:z`|múi giờ số +hh:mm (ví dụ: -04:00)|
|`%::z`|múi giờ số +hh:mm:ss (ví dụ: -04:00:00)|
|`%:::z`|múi giờ số với : đến độ chính xác cần thiết (ví dụ: -04, +05:30)|
|`%Z`|viết tắt múi giờ chữ cái (ví dụ: EDT)|