# Lệnh ``lsblk``

## Tóm tắt
Lệnh ``lsblk`` hiển thị các thiết bị block và loop trên hệ thống. Nó đặc biệt hữu ích khi bạn muốn định dạng đĩa, ghi hệ thống tệp, kiểm tra hệ thống tệp và biết điểm gắn kết của một thiết bị.

## Ví dụ

1. Sử dụng cơ bản rất đơn giản - chỉ cần thực thi 'lsblk' mà không có tùy chọn nào.
```
lsblk
```

2. Làm cho lsblk hiển thị các thiết bị trống
```
lsblk -a
```

3. Làm cho lsblk in thông tin kích thước bằng byte
```
lsblk -b
```

4. Làm cho lsblk in mô hình vùng cho mỗi thiết bị
```
lsblk -z
```

5. Làm cho lsblk bỏ qua các mục cho các thiết bị phụ
```
lsblk -d
```

6. Làm cho lsblk sử dụng ký tự ascii để định dạng cây
```
lsblk -i
```

7. Làm cho lsblk hiển thị thông tin về chủ sở hữu thiết bị, nhóm và chế độ
```
lsblk -m
```

8. Làm cho lsblk xuất các cột được chọn
```
lsblk -o NAME,SIZE
```

## Cú pháp
```
lsblk [options] [<device> ...]
```

## Đọc thông tin được cung cấp bởi ``lsblk``
Khi chạy ``lsblk`` mà không có cờ hoặc đối số dòng lệnh, nó sẽ ghi thông tin đĩa chung vào STDOUT.
Dưới đây là bảng giải thích thông tin đó:

| Tên Cột    | Ý Nghĩa                           | Giải Thích                                                |
|:----------:|:----------------------------------|:----------------------------------------------------------|
| NAME       | Tên của thiết bị.                 | Hiển thị tên của thiết bị.                                 |
| RM         | Có thể tháo rời.                  | Hiển thị 1 nếu thiết bị có thể tháo rời, 0 nếu không.      |
| SIZE       | Kích thước của thiết bị.          | Hiển thị kích thước của thiết bị.                          |
| RO         | Chỉ đọc.                          | Hiển thị 1 nếu chỉ đọc, 0 nếu không.                       |
| TYPE       | Loại thiết bị block hoặc loop.    | Hiển thị ``disk`` cho toàn bộ đĩa và ``part`` cho phân vùng.|
| MOUNTPOINTS| Nơi thiết bị được gắn kết.        | Hiển thị nơi thiết bị được gắn kết. Trống nếu không được gắn kết.|

## Đọc thông tin của một thiết bị cụ thể
``lsblk`` có thể hiển thị thông tin của một thiết bị cụ thể khi đường dẫn tuyệt đối của thiết bị được truyền vào.
Ví dụ, lệnh ``lsblk`` để hiển thị thông tin của đĩa ``sda`` là:
```
lsblk /dev/sda
```

## Các cờ hữu ích cho ``lsblk``
Dưới đây là bảng hiển thị một số cờ hữu ích có thể được sử dụng với lsblk

| **Cờ Ngắn**               | **Cờ Dài**             | **Mô Tả**                                  |
|:-------------------------:|:----------------------|:-------------------------------------------|
| ``-a``                    | ``--all``             | `lsblk` không liệt kê các thiết bị trống theo mặc định. Tùy chọn này vô hiệu hóa hạn chế này.|
| ``-b``                    | ``--bytes``           | In cột SIZE bằng byte thay vì định dạng dễ đọc cho con người.|
| ``-d``                    | ``--nodeps``          | Không in các thiết bị holder hoặc slave.   |
| ``-D``                    | ``--discard``         | In thông tin về khả năng loại bỏ (TRIM, UNMAP) cho mỗi thiết bị.|
| ``-E``                    | ``--dedup column``    | Sử dụng cột làm khóa loại bỏ trùng lặp để loại bỏ trùng lặp cây đầu ra. Nếu khóa không có sẵn cho thiết bị, hoặc thiết bị là phân vùng và thiết bị đĩa toàn bộ cha mẹ cung cấp cùng một khóa thì thiết bị luôn được in.|
| ``-e``                    | ``--exclude list``    | Loại trừ các thiết bị được chỉ định bởi danh sách số thiết bị chính, phân tách bằng dấu phẩy. Lưu ý rằng đĩa RAM (major=1) bị loại trừ theo mặc định. Bộ lọc được áp dụng cho các thiết bị cấp cao nhất.|
| ``-f``                    | ``--fs``              | Hiển thị thông tin về hệ thống tệp.        |
| ``-h``                    | ``--help``            | In văn bản trợ giúp và thoát.              |
| ``-l``                    | ``--include list``    | Hiển thị tất cả thông tin ở định dạng danh sách.|
| ``-J``                    | ``--json``            | Hiển thị tất cả thông tin ở định dạng JSON.|
| ``-l``                    | ``--list``            | Hiển thị tất cả thông tin ở định dạng danh sách.|
| ``-m``                    | ``--perms``           | Hiển thị thông tin về chủ sở hữu thiết bị, nhóm và chế độ.|
| ``-M``                    | ``--merge``           | Nhóm các cha mẹ của các cây con để cung cấp đầu ra dễ đọc hơn cho các thiết bị RAID và Multi-path. Đầu ra dạng cây là bắt buộc.|
| ``-n``                    | ``--noheadings``      | Không in dòng tiêu đề.                     |
| ``-o``                    | ``--output list``     | Chỉ định các cột đầu ra nào để in. Sử dụng `--help` để nhận danh sách tất cả các cột được hỗ trợ.|
| ``-O``                    | ``--output-all``      | Hiển thị tất cả các cột có sẵn.            |
| ``-p``                    | ``--paths``           | Hiển thị đường dẫn thiết bị tuyệt đối.     |
| ``-P``                    | ``--pairs``           | Sử dụng định dạng đầu ra key="value". Tất cả các ký tự có thể không an toàn đều được mã hóa hex (\x<code>).|
| ``-r``                    | ``--raw``             | Sử dụng định dạng đầu ra thô. Tất cả các ký tự có thể không an toàn đều được mã hóa hex (\x<code>) trong các cột NAME, KNAME, LABEL, PARTLABEL và MOUNTPOINT.|
| ``-S``                    | ``--scsi``            | Chỉ xuất thông tin về các thiết bị SCSI. Tất cả các phân vùng, thiết bị slave và holder đều bị bỏ qua.|
| ``-s``                    | ``--inverse``         | In các phụ thuộc theo thứ tự ngược lại.    |
| ``-t``                    | ``--topology``        | Xuất thông tin về cấu trúc thiết bị block. Tùy chọn này tương đương với "-o NAME,ALIGNMENT,MIN-IO,OPT-IO,PHY-SEC,LOG-SEC,ROTA,SCHED,RQ-SIZE".|
| ``-T``                    | ``--tree[=column]``   | Hiển thị tất cả thông tin ở định dạng cây. |
| ``-V``                    | ``--version``         | Xuất thông tin phiên bản và thoát.         |
| ``-w``                    | ``--width``           | Chỉ định chiều rộng đầu ra là số ký tự. Mặc định là số cột của terminal, và nếu không được thực thi trên terminal, thì chiều rộng đầu ra không bị giới hạn theo mặc định.|
| ``-x``                    | ``--sort [column]``   | Sắp xếp các dòng đầu ra theo cột. Tùy chọn này kích hoạt định dạng đầu ra `--list` theo mặc định. Có thể sử dụng tùy chọn `--tree` để buộc đầu ra dạng cây và sau đó các nhánh cây được sắp xếp theo cột.|
| ``-z``                    | ``--zoned``           | In mô hình vùng cho mỗi thiết bị.          |
| ``-``                     | ``--sysroot directory``| Thu thập dữ liệu cho một phiên bản Linux khác với phiên bản mà lệnh lsblk được phát hành. Thư mục được chỉ định là gốc hệ thống của phiên bản Linux cần kiểm tra.|

## Mã thoát
Giống như mọi chương trình Unix / Linux, ``lsblk`` trả về một mã thoát cho môi trường.
Dưới đây là bảng các mã thoát.

| Mã Thoát | Ý Nghĩa                                                    |
|:--------:|:-----------------------------------------------------------|
| 0        | Thoát thành công.                                          |
| 1        | Thoát thất bại.                                            |
| 32       | Không tìm thấy thiết bị được chỉ định.                     |
| 64       | Một số thiết bị được chỉ định được tìm thấy trong khi một số không.|