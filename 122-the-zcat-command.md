# Lệnh `zcat`

Lệnh `zcat` cho phép bạn xem nội dung của một tệp nén.

### Ví dụ:

1. Để xem nội dung của một tệp nén:

```
~$ zcat test.txt.gz
Hello World
```

2. Nó cũng có thể hoạt động với nhiều tệp:

```
~$ zcat test2.txt.gz test.txt.gz
hello
Hello world
```

### Cú pháp:

Cú pháp chung cho lệnh `zcat` như sau:

```
zcat [  -n ] [  -V ] [  File ... ]
```