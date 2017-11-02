# Github 准备 Git 客户端

Github 提供了 [GitHub Desktop](https://desktop.github.com/)。在安装过程中需要从**墙外**下载一些资源，导致安装失败。

我用的是 [Git 命令行客户端](../git/install.md)。

## SSH

Github 上的库可以使用下面地址

- HTTPS 格式为 `https://github.com/{user}/{repo}.git`
- SSH，格式为 `git@github.com:{user}/{repo}.git`

若使用 HTTPS 地址，每次 push 都要需要输入账户密码，比较麻烦（有的 Git 客户端会保存密码），使用 SSH 地址可以避免这种麻烦。

打开个人设置页面，[添加 SSH 公钥](https://github.com/settings/keys)

帮助

- <https://help.github.com/articles/connecting-to-github-with-ssh/>
- <http://www.worldhello.net/gotgithub/02-join-github/010-account-setup.html>
