
直接通过 `=` 创建的变量为局部变量，不会被子进程读取
```sh
title="Hello World"
```
可以使用 export 命令，将某个局部变量变成环境变量。环境变量可以被子进程读取。
```sh
title="Hello World"
export title
```

## 子 shell（subshell）
subshell 会完整地复制父 shell，包括父 shell 的所有变量、别名、函数等：
```bash
(ls -l)
(alias)

```

## 配置环境

* 启动文件：登录时自动执行的配置文件。仅对登录 shell 有效，所以可以设置和导出环境变量。但是，在该文件中定义别名没有任何作用，因为别名不会复制到子进程。
	* $HOME/.bash_profile
	* $HOME/.bash_login
	* $HOME/.profile
* 初始化文件：登录 shell 之外的每个 shell 实例执行的配置文件。例如，手动运行交互式 shell 或（非交互式）shell 脚本时。可以设置变量或定义别名。
	* 交互式 shell：$HOME/.bashrc
	* shell 脚本：BASH_ENV=/usr/local/etc/bashrc
* 清理文件：退出 shell 之前执行的配置文件。