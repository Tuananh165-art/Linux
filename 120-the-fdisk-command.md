# Lệnh `fdisk`

Lệnh `fdisk` được sử dụng để kiểm soát bảng phân vùng đĩa và thực hiện các thay đổi đối với nó và đây là danh sách một số tùy chọn được cung cấp bởi nó:
- Tổ chức không gian cho các ổ đĩa mới.
- Sửa đổi các ổ đĩa cũ.
- Tạo không gian cho các phân vùng mới.
- Di chuyển dữ liệu đến các phân vùng mới.

### Ví dụ:

1. Để xem chi tiết cơ bản về tất cả các phân vùng có sẵn trên hệ thống:

```
fdisk -l
```

2. Để hiển thị kích thước của phân vùng:

```
fdisk -s /dev/sda
```

3. Để xem thông báo trợ giúp và tất cả các tùy chọn của lệnh:
```
fdisk -h
```

### Cú pháp:

```
fdisk [options] device
```

### Một số tùy chọn lệnh:

Khi viết lệnh sau
```
fdisk /dev/sdb
```
cửa sổ sau sẽ xuất hiện:
![Options](https://media.geeksforgeeks.org/wp-content/uploads/20190219152451/Screenshot-711.png)
và sau đó bạn gõ m sẽ hiển thị tất cả các tùy chọn bạn cần như tạo phân vùng mới và xóa phân vùng như trong hình sau:
![Options](https://media.geeksforgeeks.org/wp-content/uploads/20190219153114/Screenshot-741.png)