
# Lệnh `mount`

Lệnh `mount` được sử dụng để gắn 'attach' một hệ thống tệp và làm cho nó có thể truy cập được bởi cấu trúc thư mục hiện có.
### Ví dụ:

1. Hiển thị thông tin phiên bản:

```
mount -V
```

2. Gắn hệ thống tệp được tìm thấy trên thiết bị và loại type tại thư mục dir:

```
mount -t type device dir
```

### Các hình thức cú pháp:

```
mount [-lhV]
```
```
mount -a [-fFnrsvw] [-t vfstype] [-O optlist]
```
```
mount [-fnrsvw] [-t fstype] [-o options] device dir
```

### Các cờ bổ sung và chức năng của chúng:

|**Cờ ngắn**   |**Cờ dài**   |**Mô tả**   |
|:---|:---|:---|
|`-h`|<center>`--help`</center>|Hiển thị thông điệp trợ giúp và thoát|
|`-n`|<center>`--no-mtab`</center>|Gắn mà không ghi vào /etc/mtab|
|`-a`|<center>`--all`</center>|Gắn tất cả các hệ thống tệp (của các loại đã cho) được đề cập trong fstab|
|`-r`|`--read-only`|Gắn hệ thống tệp chỉ đọc|
|`-w`|`--rw`|Gắn hệ thống tệp dưới dạng đọc/ghi.|
|`-M`|`--move`|Di chuyển một cây con đến một nơi khác.|
|`-B`|`--bind`|Gắn lại một cây con ở nơi khác *(để nội dung của nó có sẵn ở cả hai nơi)*.|
