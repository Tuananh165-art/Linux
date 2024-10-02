# Lệnh `banner`

Lệnh `banner` ghi các chuỗi ký tự ASCII ra đầu ra tiêu chuẩn bằng các chữ cái lớn. Mỗi dòng trong đầu ra có thể dài tới 10 ký tự chữ hoa hoặc chữ thường. Khi xuất ra, tất cả các ký tự xuất hiện dưới dạng chữ hoa, với các ký tự chữ thường đầu vào xuất hiện nhỏ hơn các ký tự chữ hoa đầu vào.

Lưu ý: Nếu bạn sẽ định nghĩa nhiều hơn một NUMBER với lệnh sleep thì lệnh này sẽ trì hoãn tổng các giá trị.

### Ví dụ:

1. Để hiển thị một banner tại trạm làm việc, nhập:

```
banner LINUX!
```

2. Để hiển thị nhiều hơn một từ trên một dòng, đặt văn bản trong dấu ngoặc kép, như sau:

```
banner "Intro to" Linux
```

> Điều này sẽ hiển thị Intro to trên một dòng và Linux trên dòng tiếp theo

3. In “101LinuxCommands” bằng các chữ cái lớn.

```
banner 101LinuxCommands
```

> Nó sẽ chỉ in 101LinuxCo vì banner có dung lượng mặc định là 10

---