# Lệnh `screen`

`screen` - Với screen, bạn có thể bắt đầu một phiên screen và sau đó mở bất kỳ số lượng cửa sổ (terminal ảo) nào bên trong phiên đó. 
Các tiến trình chạy trong Screen sẽ tiếp tục chạy khi cửa sổ của chúng không hiển thị ngay cả khi bạn bị ngắt kết nối. Điều này rất
hữu ích cho việc chạy các phiên dài như các bash script chạy rất lâu.

Để bắt đầu một phiên screen, bạn gõ `screen`, điều này sẽ mở một phiên screen mới với một terminal ảo mở.

Dưới đây là một số lệnh phổ biến nhất để quản lý các cửa sổ Linux Screen:

|**Lệnh**   |**Mô tả**   |
|:---|:---|
|`Ctrl+a`+ `c`|Tạo một cửa sổ mới (với shell).|
|`Ctrl+a`+ `"`|Liệt kê tất cả các cửa sổ.|
|`Ctrl+a`+ `0`|Chuyển sang cửa sổ 0 (theo số).|
|`Ctrl+a`+ `A`|Đổi tên cửa sổ hiện tại.|
|`Ctrl+a`+ `S`|Chia vùng hiện tại theo chiều ngang thành hai vùng.|
|`Ctrl+a`+ `'`|Chia vùng hiện tại theo chiều dọc thành hai vùng.|
|`Ctrl+a`+ `tab`|Chuyển tiêu điểm đầu vào sang vùng tiếp theo.|
|`Ctrl+a`+ `Ctrl+a`|Chuyển đổi giữa cửa sổ hiện tại và cửa sổ trước đó.|
|`Ctrl+a`+ `Q`|Đóng tất cả các vùng trừ vùng hiện tại.|
|`Ctrl+a`+ `X`|Đóng vùng hiện tại.|

## Khôi phục một phiên Linux Screen

Để khôi phục một phiên screen, bạn gõ `screen -r`, nếu bạn có nhiều hơn một phiên screen mở, bạn phải thêm 
ID phiên vào lệnh để kết nối với phiên đúng.

## Liệt kê tất cả các phiên screen đang mở

Để tìm ID phiên, bạn có thể liệt kê các phiên screen đang chạy hiện tại với:

`screen -ls`

Có các phiên screen trên:
```
18787.pts-0.your-server   (Detached)
15454.pts-0.your-server   (Detached)
2 Sockets in /run/screens/S-yourserver.
``` 

Nếu bạn muốn khôi phục screen 18787.pts-0, thì gõ lệnh sau:

`screen -r 18787`