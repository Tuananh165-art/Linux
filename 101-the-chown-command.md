# Lệnh `chown`

Lệnh `chown` cho phép thay đổi quyền sở hữu của một tệp hoặc thư mục. Người dùng và nhóm là những yếu tố cơ bản trong Linux, với `chown` bạn có thể thay đổi chủ sở hữu của một tệp hoặc thư mục. Cũng có thể thay đổi quyền sở hữu trên các thư mục một cách đệ quy.

### Ví dụ:

1. Thay đổi chủ sở hữu của một tệp

```
chown user file.txt
```

2. Thay đổi nhóm của một tệp

```
chown :group file.txt
```

3. Thay đổi người dùng và nhóm trong một dòng lệnh

```
chown user:group file.txt
```

4. Thay đổi quyền sở hữu trên một thư mục một cách đệ quy

```
chown -R user:group folder
```

### Cú pháp:

```
chown [-OPTION] [DIRECTORY_PATH]
```