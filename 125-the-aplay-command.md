# Lệnh `aplay`

`aplay` là một trình phát âm thanh dòng lệnh cho các trình điều khiển thẻ âm thanh ALSA (Advanced Linux Sound Architecture). Nó hỗ trợ nhiều định dạng tệp và nhiều thẻ âm thanh với nhiều thiết bị. Nó chủ yếu được sử dụng để phát âm thanh trên giao diện dòng lệnh. aplay tương tự như arecord chỉ khác là nó phát thay vì ghi âm. Đối với các định dạng tệp âm thanh được hỗ trợ, tốc độ lấy mẫu, độ sâu bit, v.v. có thể được xác định tự động từ tiêu đề tệp âm thanh.

## Cú pháp:

```
$ aplay [flags] [filename [filename]] ...
```

## Tùy chọn:

```
-h, –help : Hiển thị thông tin trợ giúp.
-d, –duration=# : Dừng sau # giây.
-r, –rate=# : Tốc độ lấy mẫu tính bằng Hertz. Tốc độ mặc định là 8000 Hertz.
–version : In phiên bản hiện tại.
-l, –list-devices : Liệt kê tất cả các thẻ âm thanh và thiết bị âm thanh kỹ thuật số.
-L, –list-pcms : Liệt kê tất cả các PCMs (Pulse Code Modulation) được định nghĩa.
-D, –device=NAME : Chọn PCM theo tên.
```

Lưu ý: Lệnh này chứa nhiều tùy chọn khác mà chúng ta thường không cần. Nếu bạn muốn biết thêm, bạn có thể chạy lệnh sau trên terminal của mình.

```
aplay --help
```

## Ví dụ:

1. Để phát âm thanh chỉ trong 10 giây ở tần số 2500hz.

   ```
   $ aplay -d 10 -r 2500hz sample.mp3
   ```

   > Phát tệp sample.mp3 trong 10 giây ở tần số 2500hz.

2. Để phát toàn bộ đoạn âm thanh ở tần số 2500hz.

   ```
   $ aplay -r 2500hz sample.mp3
   ```

   > Phát tệp sample.mp3 ở tần số 2500hz.

3. Để hiển thị thông tin phiên bản.

   ```
   $ aplay --version
   ```

   > Hiển thị thông tin phiên bản. Đối với tôi, nó hiển thị aplay: phiên bản 1.1.0

---