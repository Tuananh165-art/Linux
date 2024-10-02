# Lệnh `shuf`

Lệnh `shuf` trong Linux viết một hoán vị ngẫu nhiên của các dòng đầu vào ra đầu ra tiêu chuẩn. Nó giả ngẫu nhiên hóa một đầu vào theo cách tương tự như xáo bài. Nó là một phần của GNU Coreutils và không phải là một phần của POSIX. Lệnh này đọc từ một tệp hoặc đầu vào tiêu chuẩn trong bash và ngẫu nhiên hóa các dòng đầu vào đó và hiển thị đầu ra.

## Cú pháp
````

# file shuf
shuf [OPTION] [FILE]

# list shuf
shuf -e [OPTION]... [ARG]

# range shuf
shuf -i LO-HI [OPTION]
````

Giống như các lệnh Linux khác, lệnh `shuf` đi kèm với tùy chọn `--help`:
````

[user@home ~]$ shuf --help
Usage: shuf [OPTION]... [FILE]
  or:  shuf -e [OPTION]... [ARG]...
  or:  shuf -i LO-HI [OPTION]...
Write a random permutation of the input lines to standard output.

With no FILE, or when FILE is -, read standard input.

Mandatory arguments to long options are mandatory for short options too.
  -e, --echo                xử lý mỗi ARG như một dòng đầu vào
  -i, --input-range=LO-HI   xử lý mỗi số từ LO đến HI như một dòng đầu vào
  -n, --head-count=COUNT    xuất ra tối đa COUNT dòng
  -o, --output=FILE         ghi kết quả vào FILE thay vì xuất ra tiêu chuẩn
      --random-source=FILE  lấy byte ngẫu nhiên từ FILE
  -r, --repeat              các dòng xuất ra có thể được lặp lại
  -z, --zero-terminated     dấu phân cách dòng là NUL, không phải newline
````

## Ví dụ:

### Lệnh shuf không có bất kỳ tùy chọn hoặc đối số nào.

````

shuf
````

Khi lệnh `shuf` được sử dụng mà không có bất kỳ đối số nào trong dòng lệnh, nó sẽ lấy đầu vào từ người dùng cho đến khi `CTRL-D` được nhập để kết thúc tập hợp đầu vào. Nó hiển thị các dòng đầu vào dưới dạng xáo trộn. Nếu `1, 2, 3, 4 và 5` được nhập làm dòng đầu vào, thì nó sẽ tạo ra `1, 2, 3, 4 và 5` theo thứ tự ngẫu nhiên trong đầu ra như minh họa dưới đây:

````

[user@home ~]$ shuf
1
2
3
4
5

4
5
1
2
3
````

Xem xét một ví dụ nơi đầu vào được lấy từ pipe:

````

{
seq 5 | shuf
}
````

`seq 5` trả về các số nguyên theo thứ tự từ `1` đến `5` trong khi lệnh `shuf` lấy nó làm đầu vào và xáo trộn nội dung tức là các số nguyên từ `1` đến `5`. Do đó, `1` đến `5` được hiển thị dưới dạng đầu ra theo thứ tự ngẫu nhiên.

````

[user@home ~]$ {
> seq 5 | shuf
> }
5
4
2
3
1
````

### Tập tin shuf

Khi lệnh `shuf` được sử dụng mà không có tùy chọn `-e` hoặc `-i`, thì nó hoạt động như một file shuf tức là, nó xáo trộn nội dung của tệp. `<file_name>` là tham số cuối cùng của lệnh `shuf` và nếu không được cung cấp, thì đầu vào phải được cung cấp từ shell hoặc pipe.

Xem xét một ví dụ nơi đầu vào được lấy từ một tệp:

````

shuf file.txt
````

Giả sử file.txt chứa 6 dòng, thì lệnh shuf hiển thị các dòng đầu vào theo thứ tự ngẫu nhiên dưới dạng đầu ra.

````

[user@home ~]$ cat file.txt
line-1
line-2
line-3
line-4
line-5

[user@home ~]$ shuf file.txt
line-5
line-4
line-1
line-3
line-2
````

Bất kỳ số dòng nào cũng có thể được ngẫu nhiên hóa bằng cách sử dụng tùy chọn `-n`.

````

shuf -n 2 file.txt
````

Điều này sẽ hiển thị bất kỳ hai dòng ngẫu nhiên từ tệp.

````

line-5
line-2
````

### Danh sách shuf

Khi tùy chọn `-e` được sử dụng với lệnh shuf, nó hoạt động như một list shuf. Các đối số của lệnh được lấy làm dòng đầu vào cho shuf.

Xem xét một ví dụ:

````

shuf -e A B C D E
````

Nó sẽ lấy `A, B, C, D, E` làm dòng đầu vào và sẽ xáo trộn chúng để hiển thị đầu ra.

````

A
C
B
D
E
````

Bất kỳ số dòng đầu vào nào cũng có thể được hiển thị bằng cách sử dụng tùy chọn `-n` cùng với tùy chọn `-e`.

````

shuf -e -n 2 A B C D E
````

Điều này sẽ hiển thị bất kỳ hai trong số các đầu vào.

````

E
A
````

### Phạm vi shuf

Khi tùy chọn `-i` được sử dụng cùng với lệnh `shuf`, nó hoạt động như một `range shuf`. Nó yêu cầu một phạm vi đầu vào làm đầu vào trong đó `L0` là giới hạn dưới trong khi `HI` là giới hạn trên. Nó hiển thị các số nguyên từ `L0-HI` dưới dạng xáo trộn.

````

[user@home ~]$ shuf -i 1-5
4
1
3
2
5
````

## Kết luận

Lệnh `shuf` giúp bạn ngẫu nhiên hóa các dòng đầu vào. Và có các tính năng để giới hạn số dòng đầu ra, lặp lại các dòng và thậm chí tạo ra các số nguyên dương ngẫu nhiên. Khi bạn đã thực hành xong những gì chúng tôi đã thảo luận ở đây, hãy truy cập trang [man page](https://linux.die.net/man/1/shuf) của công cụ để biết thêm về nó.
````