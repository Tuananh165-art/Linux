# Lệnh `cmp`

Lệnh `cmp` được sử dụng để so sánh hai tệp byte theo byte.

Ví dụ:
```
cmp file1.txt file2.txt
```

Cú pháp:
```
cmp [option] File1 File2
```

## Một số ví dụ:

1. ### So sánh hai tệp:

Thực hiện so sánh đơn giản của hai tệp để kiểm tra xem chúng có khác nhau hay không.

Ví dụ:
```
cmp File1 File2
```

2. ### So sánh các tệp sau khi bỏ qua một số byte nhất định:

So sánh hai tệp sau khi bỏ qua một số byte nhất định

Ví dụ:
```
cmp -i 2 list.txt list2.txt
```

Ở đây “INT” đại diện cho số byte cần bỏ qua

3. ### Hiển thị các byte khác nhau của các tệp trong đầu ra:

Ví dụ: 
```
cmp -b list.txt list1.txt
```
4. ### Hiển thị số byte và giá trị byte khác nhau của các tệp trong đầu ra:

Ví dụ: 
```
cmp -l list.txt list1.txt
```

5. ### So sánh số byte đầu tiên của các tệp:

Ví dụ:
```
cmp -n 10 list.txt list2.txt 
```
### Các cờ bổ sung và chức năng của chúng

|**Cờ ngắn**   |**Cờ dài**   |**Mô tả**   |
|:---|:---|:---|
|`-b`|`--print-bytes`|in các byte khác nhau|
|`-i`|`--ignore-initial=SKIP`|bỏ qua số byte đầu tiên của cả hai đầu vào|
|`-i`|`--ignore-initial=SKIP1:SKIP2`|bỏ qua số byte đầu tiên của FILE1 và số byte đầu tiên của FILE2|
|`-l`|`--verbose`|hiển thị số byte và giá trị byte khác nhau|
|`-n`|`--bytes=LIMIT`|so sánh tối đa số byte LIMIT|
|`-s`|`--quiet, --silent`|ẩn tất cả các đầu ra thông thường|
|`v`|`--version`|hiển thị thông tin phiên bản và thoát|
||`--help`|Hiển thị trợ giúp này và thoát|