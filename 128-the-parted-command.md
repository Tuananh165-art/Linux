# Lệnh `parted`

Lệnh `parted` được sử dụng để quản lý các phân vùng ổ cứng trên Linux. Nó có thể được sử dụng để thêm, xóa, thu nhỏ và mở rộng các phân vùng đĩa cùng với các hệ thống tệp nằm trên chúng.
Bạn sẽ cần quyền root để chạy các lệnh `parted`.

**LƯU Ý:** Parted ghi các thay đổi ngay lập tức vào đĩa của bạn, hãy cẩn thận khi bạn đang sửa đổi các phân vùng đĩa.
### Ví dụ:

1. Hiển thị bố cục phân vùng của tất cả các thiết bị khối:
```
sudo parted -l
```

2. Hiển thị bảng phân vùng của một `disk` cụ thể
```
sudo parted disk print
```

Ví dụ về `disk` là /dev/sda, /dev/sdb

3. Tạo nhãn đĩa mới của `label-type` cho một đĩa cụ thể
```
sudo parted mklabel disk label-type
```
  
`label-type` có thể nhận các giá trị "aix", "amiga", "bsd", "dvh", "gpt", "loop", "mac", "msdos", "pc98", hoặc "sun" <br />

4. Tạo một phân vùng mới trong một `disk` cụ thể của loại `part-type`, hệ thống tệp là `fs-type` và kích thước `size` Mb.
```
sudo parted disk mkpart part-type fs-type 1 size
```
  
`part-type` có thể nhận các giá trị "primary", "logical", "extended".<br />
`fs-type` là tùy chọn. Nó có thể nhận các giá trị "btrfs", "ext2", "ext3", "ext4", "fat16", "fat32", "hfs", "hfs+", "linux-swap", "ntfs", "reiserfs", "udf", hoặc "xfs"<br />
`size` phải nhỏ hơn tổng kích thước của đĩa được chỉ định. Để tạo một phân vùng có kích thước 50Mb, <size> sẽ nhận giá trị 50
  
5. `parted` cũng có thể được chạy ở định dạng tương tác. Các thao tác để quản lý các phân vùng đĩa có thể được thực hiện bằng cách nhập các lệnh thích hợp trong phiên tương tác. 
  Lệnh `help` trong phiên tương tác hiển thị danh sách tất cả các thao tác quản lý đĩa có thể được thực hiện.
```
  $ sudo parted
  GNU Parted 3.3
  Using /dev/sda
  Welcome to GNU Parted! Type 'help' to view a list of commands.
  (parted) print  # in bảng phân vùng của đĩa mặc định đã chọn - /dev/sda                                                  
  Model: ATA VBOX HARDDISK (scsi)
  Disk /dev/sda: 53.7GB
  Sector size (logical/physical): 512B/512B
  Partition Table: msdos
  Disk Flags: 

  Number  Start   End     Size    Type     File system  Flags
   1      1049kB  53.7GB  53.7GB  primary  ext4         boot

  (parted) select /dev/sdb  # thay đổi đĩa hiện tại mà các thao tác phải được thực hiện                                                 
  Using /dev/sdb
  (parted) quit  # thoát phiên tương tác
```

### Các hình thức cú pháp:
```
parted [options] [device [command [options...]...]]
```
  
### Tuỳ chọn:
|**Tham số ngắn**   |**Tham số dài**   |**Mô tả**   |
|:---|:---|:---|
|-h|--help|hiển thị một thông báo trợ giúp liệt kê tất cả các `commands [options]` có thể|
|-l|--list|liệt kê bố cục phân vùng trên tất cả các thiết bị khối|
|-m|--machine|hiển thị đầu ra có thể phân tích bằng máy|
|-v|--version|hiển thị phiên bản|
|-a|--align|đặt loại căn chỉnh cho phân vùng mới được tạo. Nó có thể nhận các giá trị sau:<br /> `none`: Sử dụng căn chỉnh tối thiểu được phép bởi loại đĩa<br /> `cylinder`: Căn chỉnh các phân vùng với các xi lanh<br /> `minimal`: Sử dụng căn chỉnh tối thiểu như được cung cấp bởi thông tin cấu trúc đĩa<br /> `optimal`: Sử dụng căn chỉnh tối ưu như được cung cấp bởi thông tin cấu trúc đĩa|