# Lệnh `sed`

Lệnh `sed` là viết tắt của stream editor. Một stream editor được sử dụng để thực hiện các biến đổi văn bản cơ bản trên một luồng đầu vào (một tệp hoặc đầu vào từ một pipeline). Ví dụ, nó có thể thực hiện nhiều chức năng trên các tệp như tìm kiếm, tìm và thay thế, chèn hoặc xóa. Mặc dù theo một số cách nó tương tự như một trình soạn thảo cho phép chỉnh sửa kịch bản (như `ed`), `sed` hoạt động bằng cách chỉ thực hiện một lần duy nhất trên đầu vào, và do đó hiệu quả hơn. Nhưng khả năng lọc văn bản trong một pipeline của `sed` đặc biệt phân biệt nó với các loại trình soạn thảo khác.

Cách sử dụng phổ biến nhất của lệnh `sed` là để thay thế hoặc tìm và thay thế. Bằng cách sử dụng `sed`, bạn có thể chỉnh sửa tệp mà không cần mở nó, đây là một cách nhanh hơn nhiều để tìm và thay thế một cái gì đó trong tệp. Nó hỗ trợ các biểu thức chính quy cơ bản và mở rộng cho phép bạn khớp các mẫu phức tạp. Hầu hết các bản phân phối Linux đi kèm với GNU và `sed` được cài đặt sẵn theo mặc định.

### Ví dụ:

1. Để Tìm và Thay thế Chuỗi với `sed`
```
sed -i 's/{search_regex}/{replace_value}/g' input-file
```

2. Để Tìm và Thay thế Đệ quy *(cùng với `find`)*

> Đôi khi bạn có thể muốn tìm kiếm đệ quy các thư mục để tìm các tệp chứa một chuỗi và thay thế chuỗi trong tất cả các tệp. Điều này có thể được thực hiện bằng cách sử dụng các lệnh như find để tìm đệ quy các tệp trong thư mục và chuyển tên tệp cho `sed`.
Lệnh sau sẽ tìm kiếm đệ quy các tệp trong thư mục làm việc hiện tại và chuyển tên tệp cho `sed`. Nó sẽ tìm kiếm đệ quy các tệp trong thư mục làm việc hiện tại và chuyển tên tệp cho `sed`.

```
find . -type f -exec sed -i 's/{search_regex}/{replace_value}/g' {} +
```

### Cú pháp:

```
sed [OPTION]... {script-only-if-no-other-script} [INPUT-FILE]... 
```

- `OPTION` - sed options in-place, silent, follow-symlinks, line-length, null-data ...etc.
- `{script-only-if-no-other-script}` - Add the script to command if available.
- `INPUT-FILE` - Input Stream, A file or input from a pipeline.

Nếu không có tùy chọn nào được đưa ra, thì đối số không phải tùy chọn đầu tiên được coi là kịch bản sed để diễn giải. Tất cả các đối số còn lại là tên của các tệp đầu vào; nếu không có tệp đầu vào nào được chỉ định, thì đầu vào tiêu chuẩn sẽ được đọc.

Trang chủ GNU sed: [http://www.gnu.org/software/sed/](http://www.gnu.org/software/sed/)

|**Cờ ngắn**   |**Cờ dài**   |**Mô tả**   |
|:---|:---|:---|
|`-i[SUFFIX]`|<center>--in-place[=SUFFIX]</center>|Chỉnh sửa tệp tại chỗ (tạo bản sao lưu nếu cung cấp SUFFIX).|
|`-n`|<center>--quiet, --silent</center>|Ngăn chặn tự động in không gian mẫu.|
|`-e script`|<center>--expression=script</center>|Thêm kịch bản vào các lệnh sẽ được thực thi.|
|`-f script-file`|<center>--file=script-file</center>|Thêm nội dung của tệp kịch bản vào các lệnh sẽ được thực thi.|
|`-l N`|<center>--line-length=N</center>|Chỉ định độ dài dòng mong muốn cho lệnh `l`.|
|`-r`|<center>--regexp-extended</center>|Sử dụng các biểu thức chính quy mở rộng trong kịch bản.|
|`-s`|<center>--separate</center>|Xem các tệp là riêng biệt thay vì là một luồng liên tục dài duy nhất.|
|`-u`|<center>--unbuffered</center>|Tải lượng dữ liệu tối thiểu từ các tệp đầu vào và xả bộ đệm đầu ra thường xuyên hơn.|
|`-z`|<center>--null-data</center>|Tách các dòng bằng các ký tự NULL.|

### Trước khi bạn bắt đầu

Nó có thể trông phức tạp và phức tạp lúc đầu, nhưng tìm kiếm và thay thế văn bản trong các tệp với sed rất đơn giản.

Để tìm hiểu thêm: [https://www.gnu.org/software/sed/manual/sed.html](https://www.gnu.org/software/sed/manual/sed.html)