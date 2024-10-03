# Lệnh `vim`

[vim](https://www.vim.org/) là một trình soạn thảo văn bản cho Unix đi kèm với Linux, BSD và macOS. Nó được biết đến là nhanh và mạnh mẽ, một phần vì nó là một chương trình nhỏ có thể chạy trong terminal (mặc dù nó có giao diện đồ họa). Trình soạn thảo văn bản Vim được phát triển bởi [Bram Moolenaar](https://en.wikipedia.org/wiki/Bram_Moolenaar). Nó hỗ trợ hầu hết các loại tệp và trình soạn thảo vim cũng được biết đến như là trình soạn thảo của lập trình viên. Điều này chủ yếu là vì nó có thể được quản lý hoàn toàn mà không cần menu hoặc chuột với bàn phím.

**Lưu ý:** Đừng nhầm lẫn `vim` với `vi`. `vi`, viết tắt của "Visual", là một trình soạn thảo văn bản được phát triển bởi [Bill Joy](https://en.wikipedia.org/wiki/Bill_Joy) vào năm 1976. `vim` viết tắt của "Vi Improved", và là một bản sao cải tiến của trình soạn thảo `vi`.

### Câu hỏi được tìm kiếm nhiều nhất về ```vim```:
``Làm thế nào để thoát khỏi trình soạn thảo vim?``

Câu hỏi được tìm kiếm nhiều nhất về trình soạn thảo vim trông rất buồn cười nhưng thực tế là người dùng mới bị mắc kẹt ngay từ đầu khi sử dụng trình soạn thảo vim.

Lệnh để lưu tệp và thoát khỏi trình soạn thảo vim: ```:wq```

Lệnh để thoát khỏi trình soạn thảo vim mà không lưu tệp: ```:q!```

#### Đọc vui:
Đây là một [khảo sát](https://stackoverflow.blog/2017/05/23/stack-overflow-helping-one-million-developers-exit-vim/) cho cùng một câu hỏi, hãy xem và đừng nghĩ đến việc bỏ trình soạn thảo vim.

### Cài đặt:
Đầu tiên kiểm tra xem vim đã được cài đặt hay chưa, nhập lệnh sau:
```
vim --version
```
Nếu nó đã được cài đặt, nó sẽ hiển thị phiên bản của nó, nếu không chúng ta có thể chạy các lệnh dưới đây để cài đặt:

Trên Ubuntu/Debian:

```
sudo apt-get install vim
```

Trên CentOS/Fedora:

```
sudo yum install vim
```
Nếu bạn muốn sử dụng các tính năng nâng cao trên CentOS/Fedora, bạn sẽ cần cài đặt trình soạn thảo vim nâng cao, để làm điều này hãy chạy lệnh sau:

```
sudo yum install -y vim-enhanced
```

### Cú pháp:

```
vim [FILE_PATH/FILE_NAME]
```

### Ví dụ:

1. Để mở tệp có tên "demo.txt" từ thư mục hiện tại của bạn:

```
vim demo.txt
```

2. Để mở tệp trong một thư mục cụ thể:

```
vim {File_Path/filename}
```

3. Để mở tệp bắt đầu từ một dòng cụ thể trong tệp:

```
vim {File_Path/filename} +LINE_NUMBER
```
### Các chế độ trong trình soạn thảo vim:
Có một số tranh luận về số lượng chế độ mà vim có, nhưng các chế độ bạn có khả năng sử dụng nhất là ```command mode``` và ```insert mode```. Các [chế độ](https://www.freecodecamp.org/news/vim-editor-modes-explained/) này sẽ cho phép bạn làm hầu hết mọi thứ bạn cần, bao gồm tạo tài liệu của bạn, lưu tài liệu của bạn và thực hiện chỉnh sửa nâng cao, bao gồm tận dụng các chức năng tìm kiếm và thay thế.

### Quy trình làm việc của trình soạn thảo `vim`:
1. Mở một tệp mới hoặc tệp hiện có với ```vim filename```.
2. Gõ ```i``` để chuyển sang chế độ chèn để bạn có thể bắt đầu chỉnh sửa tệp.
3. Nhập hoặc sửa đổi văn bản của tệp của bạn.
4. Khi bạn hoàn thành, nhấn phím ```Esc``` để thoát khỏi chế độ chèn và quay lại chế độ lệnh.
5. Gõ :w hoặc :wq để lưu tệp hoặc lưu và thoát khỏi tệp tương ứng.

### Đào tạo tương tác

Trong hướng dẫn tương tác này, bạn sẽ học các cách khác nhau để sử dụng lệnh `vim`:

[Hướng dẫn Open vim](https://www.openvim.com/)

### Các tham số và chức năng bổ sung:

|**Tham số/Tùy chọn**  |<center>**Mô tả**</center>   |
|:---|:---|
|`-e`|Bắt đầu ở chế độ Ex (xem [Ex-mode](http://vimdoc.sourceforge.net/htmldoc/intro.html#Ex-mode))|
|`-R`|Bắt đầu ở chế độ chỉ đọc|
|`-R`|Bắt đầu ở chế độ chỉ đọc|
|`-g`|Bắt đầu [GUI](http://vimdoc.sourceforge.net/htmldoc/gui.html#GUI)|
|`-eg`|Bắt đầu GUI ở chế độ Ex|
|`-Z`|Giống như "vim", nhưng ở chế độ hạn chế|
|`-d`|Bắt đầu ở chế độ diff [diff-mode](http://vimdoc.sourceforge.net/htmldoc/diff.html#diff-mode)|
|`-h`|Hiển thị thông báo sử dụng (trợ giúp) và thoát|
|`+NUMBER`|Mở một tệp và đặt con trỏ trên dòng số được chỉ định bởi NUMBER|

### Đọc thêm về vim:

vim không thể học trong một ngày, sử dụng trong các nhiệm vụ hàng ngày để làm quen với trình soạn thảo vim.

Để tìm hiểu thêm về ```vim``` hãy theo dõi bài viết sau:

[Bài viết của Daniel Miessler](https://danielmiessler.com/study/vim/) 