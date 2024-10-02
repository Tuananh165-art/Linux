# Lệnh `expr`

Lệnh `expr` đánh giá một biểu thức đã cho và hiển thị kết quả tương ứng của nó. Nó được sử dụng cho các phép toán cơ bản như cộng, trừ, nhân, chia và chia lấy dư trên các số nguyên và đánh giá các biểu thức chính quy, các thao tác chuỗi như chuỗi con, độ dài của chuỗi, v.v.

## Cú pháp

```
expr expression
```

## Một số ví dụ:
1. ### Thực hiện các phép toán số học cơ bản bằng lệnh expr
```
expr 7 + 14
expr 7 * 8
```

2. ### So sánh hai biểu thức
```
x=10
y=20
res=`expr $x = $y`
echo $res
```

3. ### So khớp số ký tự trong hai chuỗi
```
expr alphabet : alpha
```
4. ### Tìm giá trị chia lấy dư
```
expr 20 % 30  
```
5. ### Trích xuất chuỗi con
```
a=HelloWorld
b=`expr substr $a 6 10`
echo $b
```
### Các cờ bổ sung và chức năng của chúng

|**Cờ** |**Mô tả**   |
:---|:---|
|`--version`|hiển thị thông tin phiên bản và thoát|
|`--help`|Hiển thị trợ giúp này và thoát|

Để biết thêm chi tiết: [Expr trên Wikipedia](https://en.wikipedia.org/wiki/Expr)
