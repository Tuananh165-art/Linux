# Lệnh `Wait`

Đây là một lệnh chờ hoàn thành bất kỳ tiến trình nào đang chạy của id được cung cấp. Nếu id tiến trình không được cung cấp thì nó sẽ chờ tất cả các tiến trình con hiện tại hoàn thành.

## Ví dụ

Ví dụ này cho thấy cách lệnh `wait` hoạt động: <br />

**Bước-1**:

Tạo một tệp có tên "wait_example.sh" và thêm kịch bản sau vào đó.

```
#!/bin/bash
echo "Wait command" &
process_id=$!
wait $process_id
echo "Exited with status $?"
```

**Bước-2**:

Chạy tệp với lệnh bash.

```
$ bash wait_example.sh
```