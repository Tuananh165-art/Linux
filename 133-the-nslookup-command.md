# Lệnh `nslookup`

Lệnh `nslookup` là một công cụ dòng lệnh quản trị mạng để truy vấn Hệ thống Tên Miền (DNS) nhằm lấy thông tin ánh xạ tên miền hoặc địa chỉ IP hoặc bất kỳ bản ghi DNS cụ thể nào khác.

## Cú pháp

```
nslookup [options] [host]
```

## Các tùy chọn
Một số cờ tùy chọn phổ biến bao gồm:

```
-domain=[domain-name]	Thay đổi tên DNS mặc định.
-debug	Hiển thị thông tin gỡ lỗi.
-port=[port-number]	Chỉ định cổng cho các truy vấn. Số cổng mặc định là 53.
-timeout=[seconds]	Chỉ định thời gian cho phép máy chủ phản hồi.
-type=a	Xem thông tin về các bản ghi địa chỉ DNS A.
-type=any	Xem tất cả các bản ghi có sẵn.
-type=hinfo	Xem thông tin liên quan đến phần cứng của máy chủ.
-type=mx	Xem thông tin máy chủ Mail Exchange.
-type=ns	Xem các bản ghi Máy chủ Tên.
-type=ptr	Xem các bản ghi Con trỏ. Được sử dụng trong tra cứu DNS ngược.
-type=soa	Xem các bản ghi Khởi đầu Ủy quyền.
```

## Một số ví dụ:
1. Truy vấn máy chủ DNS
```
nslookup www.google.com
```

2. Chỉ định một cổng để truy vấn
```
nslookup -port=53 www.google.com
```

3. Lấy bản ghi MX
```
nslookup -type=mx google.com
```

Ở đây tôi đã chỉ cho bạn cách sử dụng lệnh nslookup trong Linux. Mặc dù có các công cụ tra cứu DNS khác, chẳng hạn như dig, nslookup có thể là một lựa chọn tốt hơn vì nó là một công cụ mạnh mẽ có mặt trong hầu hết mọi hệ thống.

Để biết thêm chi tiết: [Nslookup trên Wikipedia](https://en.wikipedia.org/wiki/Nslookup)