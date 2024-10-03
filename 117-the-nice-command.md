
# Lệnh `nice/renice`

Lệnh `nice/renice` được sử dụng để thay đổi mức độ ưu tiên của chương trình sẽ được thực thi. 
Phạm vi ưu tiên là từ -20 đến 19, trong đó 19 là mức độ ưu tiên thấp nhất.
### Ví dụ:


1. Chạy lệnh cc trong nền với mức độ ưu tiên thấp hơn mặc định (chậm hơn):

```

nice -n 15 cc -c *.c &
```

2. Tăng mức độ ưu tiên cho tất cả các tiến trình thuộc nhóm "test":


```

renice --20 -g test

```

### Cú pháp:


```
nice [  -Increment|  -n Increment ] Command [ Argument ... ]
```


### Tham số : 


|**Tham số ngắn**   |**Tham số dài**   |**Mô tả**   |
|:---|:---|:---|

|`-Increment`|<center>-</center>|Increment là giá trị của mức độ ưu tiên bạn muốn gán.|
|`-n Increment`|<center>-</center>|Giống như `-Increment`

