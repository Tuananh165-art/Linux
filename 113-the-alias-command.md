# Lệnh `alias`

Lệnh `alias` cho phép bạn tạo các phím tắt cho các lệnh hoặc định nghĩa các lệnh của riêng bạn.  
Điều này chủ yếu được sử dụng để tránh gõ các lệnh dài.

### Ví dụ:

1. Để hiển thị danh sách tất cả các alias đã được định nghĩa dưới dạng có thể tái sử dụng `alias NAME=VALUE`:

```
alias -p
```

2. Để tạo phím tắt cho `ls -A`:

```
alias la='ls -A'
```

### Cú pháp:

```
alias [-p] [name[=value]]
```

### Thiết lập các tùy chọn cố định:

Như với hầu hết các thiết lập tùy chỉnh của Linux cho terminal, bất kỳ alias nào bạn định nghĩa chỉ được áp dụng cho phiên terminal hiện tại.

Để bất kỳ alias nào có hiệu lực cho tất cả các phiên mới, bạn cần thêm lệnh đó vào tệp rc của bạn để được thực thi trong quá trình khởi động của mỗi phiên terminal mới.
tệp này có thể là:
- **Bash**: ~/.bashrc
- **ZSH**: ~/.zshrc
- **Fish** – ~/.config/fish/config.fish

bạn có thể mở tệp đó bằng trình soạn thảo yêu thích của mình như sau:

```
vim ~/.bashrc
```
gõ các lệnh của bạn mỗi lệnh một dòng, sau đó lưu tệp và thoát.
các lệnh sẽ được tự động áp dụng trong phiên tiếp theo.

Nếu bạn muốn áp dụng nó trong phiên hiện tại, chạy lệnh sau:
```
source ~/.bashrc
```

### Lệnh ngược lại:
Để xóa alias đã được định nghĩa, bạn có thể sử dụng lệnh `unalias` như sau:
```
unalias alias_name
```

để xóa tất cả các alias
```
unalias -a
```