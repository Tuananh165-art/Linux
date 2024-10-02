# Lệnh `fold`

Lệnh `fold` trong Linux gói mỗi dòng trong một tệp đầu vào để phù hợp với chiều rộng được chỉ định và in nó ra đầu ra tiêu chuẩn.

Theo mặc định, nó gói các dòng ở chiều rộng tối đa là 80 cột nhưng điều này có thể cấu hình được.

Để gói đầu vào bằng lệnh fold, hãy chuyển một tệp hoặc đầu vào tiêu chuẩn cho lệnh.


### Cú pháp:

```
fold [OPTION]... [FILE]...
```

### Tùy chọn

**-w** : Bằng cách sử dụng tùy chọn này trong lệnh fold, chúng ta có thể giới hạn chiều rộng bằng số cột.

Bằng cách sử dụng lệnh này, chúng ta thay đổi chiều rộng cột từ chiều rộng mặc định là 80.
Cú pháp:

```
fold -w[n] [FILE]
```
Ví dụ: gói các dòng của file1.txt thành chiều rộng 60 cột

```
fold -w60 file1.txt
```


**-b** : Tùy chọn này của lệnh fold được sử dụng để giới hạn chiều rộng của đầu ra bằng số byte thay vì số cột.

Bằng cách sử dụng tùy chọn này, chúng ta có thể áp đặt chiều rộng của đầu ra theo số byte.

```
fold -b[n] [FILE]
```

Ví dụ: giới hạn chiều rộng đầu ra của tệp thành 40 byte và lệnh sẽ ngắt đầu ra ở 40 byte.

```
fold -b40 file1.txt
```

**-s** : Tùy chọn này được sử dụng để ngắt các dòng trên các khoảng trắng để các từ không bị ngắt.

Nếu một đoạn của dòng chứa một ký tự trống trong vòng các vị trí cột chiều rộng đầu tiên, hãy ngắt dòng sau ký tự trống cuối cùng đáp ứng các ràng buộc chiều rộng.

```
fold -w[n] -s [FILE]
```