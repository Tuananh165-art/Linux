# Lệnh `make`

Lệnh `make` được sử dụng để tự động hóa việc tái sử dụng nhiều lệnh trong cấu trúc thư mục nhất định.

Một ví dụ cho điều đó là việc sử dụng `terraform init`, `terraform plan`, và `terraform validate` trong khi phải thay đổi các đăng ký khác nhau trong Azure. Điều này thường được thực hiện theo các bước sau:

```
az account set --subscription "Subscription - Name"
terraform init
```

Cách mà lệnh `make` có thể giúp chúng ta là nó có thể tự động hóa tất cả những điều đó chỉ trong một lần:
```make tf-init```

### Cú pháp:

```
make [ -f makefile ] [ options ] ... [ targets ] ...
```

### Ví dụ sử dụng (hướng dẫn):

#### 1. Tạo `Makefile` trong thư mục hướng dẫn của bạn
#### 2. Bao gồm những điều sau trong `Makefile` của bạn:
```
hello-world:
        echo "Hello, World!"

hello-bobby:
        echo "Hello, Bobby!"

touch-letter:
        echo "This is a text that is being inputted into our letter!" > letter.txt

clean-letter:
        rm letter.txt
```
#### 3. Thực hiện ```make hello-world``` - điều này sẽ in "Hello, World" trong terminal của chúng ta.
#### 4. Thực hiện ```make hello-bobby``` - điều này sẽ in "Hello, Bobby!" trong terminal của chúng ta.
#### 5. Thực hiện ```make touch-letter``` - Điều này sẽ tạo một tệp văn bản tên là `letter.txt` và điền một dòng vào đó.
#### 6. Thực hiện ```make clean-letter``` - điều này sẽ xóa tệp `letter.txt`.

### Tham khảo các hướng dẫn dài hơn và nhiều nội dung hơn:

(linoxide - ví dụ lệnh make trong linux)[https://linoxide.com/linux-make-command-examples/]
(makefiletutorial.com - tên của nó đã nói lên tất cả)[https://makefiletutorial.com/]