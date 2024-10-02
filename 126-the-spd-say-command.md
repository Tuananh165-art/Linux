# Lệnh `spd-say`

`spd-say` gửi yêu cầu đầu ra văn bản thành giọng nói đến quá trình speech-dispatcher xử lý nó và lý tưởng là xuất kết quả ra hệ thống âm thanh.

## Cú pháp:

```
$ spd-say [options] "some text"
```

## Tuỳ chọn:

```
-r, --rate
       Đặt tốc độ của giọng nói (giữa -100 và +100, mặc định: 0)

-p, --pitch
       Đặt cao độ của giọng nói (giữa -100 và +100, mặc định: 0)

-i, --volume
       Đặt âm lượng (cường độ) của giọng nói (giữa -100 và +100, mặc định: 0)

-o, --output-module
       Đặt mô-đun đầu ra

-l, --language
       Đặt ngôn ngữ (mã iso)

-t, --voice-type
       Đặt loại giọng nói ưa thích (male1, male2, male3, female1, female2, female3,
       child_male, child_female)

-m, --punctuation-mode
       Đặt chế độ dấu câu (none, some, all)

-s, --spelling
       Đánh vần tin nhắn

-x, --ssml
       Bật chế độ SSML (mặc định: tắt)

-e, --pipe-mode
       Đường ống từ stdin đến stdout cộng với Speech Dispatcher

-P, --priority
       Đặt mức độ ưu tiên của tin nhắn (important, message, text, notification, progress;
       mặc định: text)

-N, --application-name
       Đặt tên ứng dụng được sử dụng để thiết lập kết nối với giá trị chuỗi được chỉ định
       (mặc định: spd-say)

-n, --connection-name
       Đặt tên kết nối được sử dụng để thiết lập kết nối với giá trị chuỗi được chỉ định
       (mặc định: main)

-w, --wait
       Chờ cho đến khi tin nhắn được nói hoặc bị loại bỏ

-S, --stop
       Dừng nói tin nhắn đang được nói trong Speech Dispatcher

-C, --cancel
       Hủy tất cả các tin nhắn trong Speech Dispatcher

-v, --version
       In thông tin phiên bản và bản quyền

-h, --help
       In thông tin này
```

## Ví dụ:

1. Để phát văn bản đã cho dưới dạng âm thanh.

```
$ spd-say "Hello"
```

>Phát "Hello" dưới dạng âm thanh.
````
`````