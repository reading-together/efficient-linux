
## 定义变量

```sh
$ work=$HOME/Projects
```

定义变量时，等号左右不能有空格。否则，shell 会以为命令行的第一个单词是运行的程序，而等号和值是该程序的参数：
```sh
$ work = $HOME/Projects
work: command not found
```

## 输出变量，shell 会干什么？

当通过 `echo` 输出变量时：
```sh
$ echo $HOME
/home/kang
```

并不是 `echo` 将 `$HOME` 解析成了 `/home/kang`，实际上是 shell 在运行 `echo` 之前，求出了 `$HOME` 的值。所以在 `echo` 看来，输入的命令是：
```sh
$ echo /home/kang
```