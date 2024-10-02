# Lệnh `chmod`

Lệnh `chmod` cho phép bạn thay đổi quyền trên một tệp bằng cách sử dụng chế độ ký hiệu hoặc chế độ số hoặc tệp tham chiếu.

### Ví dụ:

1. Thay đổi quyền của một tệp bằng chế độ ký hiệu:

```
chmod u=rwx,g=rx,o=r myfile
```

Lệnh trên có nghĩa là:

- người dùng có thể đọc, ghi, thực thi `myfile`
- nhóm có thể đọc, thực thi `myfile`
- người khác có thể đọc `myfile`

2. Thay đổi quyền của một tệp bằng chế độ số

```
chmod 754 myfile user:group file.txt
```

Lệnh trên có nghĩa là:

- người dùng có thể đọc, ghi, thực thi `myfile`
- nhóm có thể đọc, thực thi `myfile`
- người khác có thể đọc `myfile`

3. Thay đổi quyền của một thư mục đệ quy

```
chmod -R 754 folder
```

### Cú pháp:

```
chmod [OPTIONS] MODE FILE(s)
```

- `[OPTIONS]` :
  `-R`: đệ quy, nghĩa là tất cả các tệp bên trong thư mục

- `MODE`: các cách khác nhau để đặt quyền:

- **Chế độ ký hiệu được giải thích**

  - u: người dùng
  - g: nhóm
  - o: người khác
  - =: đặt quyền
  - r: đọc
  - w: ghi
  - x: thực thi
  - ví dụ `u=rwx` nghĩa là người dùng có thể đọc, ghi và thực thi

- **Chế độ số được giải thích**:
  
Chế độ số dựa trên biểu diễn nhị phân của các quyền cho người dùng, nhóm và người khác, để biết thêm thông tin vui lòng xem [giải thích](https://www.digitalocean.com/community/tutorials/linux-permissions-basics-and-how-to-use-umask-on-a-vps#types-of-permissions) từ phần cộng đồng của Digital Ocean:

  - 4 đại diện cho "đọc",
  - 2 đại diện cho "ghi",
  - 1 đại diện cho "thực thi", và
  - 0 đại diện cho "không có quyền."
  - ví dụ 7 nghĩa là đọc + ghi + thực thi