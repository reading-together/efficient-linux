

## 重定向会导致 ls 的行为改变

`ls` 知道自己的标准输出屏幕还是被重定向了。原因是为了用户友好：

当标准输出为屏幕时，ls 就会将输出排列成多列，以方便用户阅读:

> 使用选项 `-1` 可以强制 ls 输出结果到一列上

```bash
$ ls /bin
bash    dif    kmod    networkctl     red   tar
bsd-csh dmesg  less    nisdomainname  rm    tempfile
.
.
.
```

然而，当标准输出被重定向时，ls 就只有一列输出:

> 使用选项 `-C` 可以强制 ls 输出多列结果。

```bash
$ ls /bin | cat
bash
bsd-csh
bunzip2
busybox
.
.
.
```
