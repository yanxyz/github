# 安装 git

[Git 客户端列表](https://git-scm.com/downloads)

### Git for Windows

Git for Windows 是 Git 命令行工具。

[下载安装程序](https://github.com/git-for-windows/git/releases)

在安装过程中

- PATH 选择 "Use Git from the Windows Command Prompt"。有些程序会用到 git，比如 npm 从 Github 安装模块。
- line ending conversions 选择 "Checkout as-it, Commit as-it"。不让 git 转换 line ending 。代码编辑器只要合格就不应该有问题。

安装完成后，在终端中运行

```sh
git --help
```

### TortoiseSVN

TortoiseGit 为 Git GUI 工具，类似于 TortoiseSVN。

[下载](http://code.google.com/p/tortoisegit/downloads/list)。

TortoiseGit 自带了 TortoisePlink.exe 来实现 SSH 传输。可以换成 Putty，打开上下文菜单 `TortoiseGit -> Settings -> Network -> SSH -> SSH client`。在 Windows 开始菜单中找到并运行 PuTTYgen， 生成一对公钥和私钥，私钥保存为 `.ppk` 格式文件，公钥保存到服务器（Github 在个人设置页面[添加公钥](https://github.com/settings/keys)）。

[重装 TortoiseGit 之后不能选择 SSH client](http://stackoverflow.com/questions/13653319/cannot-pick-an-ssh-client-when-installing-tortoisegit)
