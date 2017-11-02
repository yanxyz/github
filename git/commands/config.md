# Git config

git 配置文件有四处

1. `$(prefix)/etc/gitconfig`，系统配置文件，对应选项 `--system`。
1. `$XDG_CONFIG_HOME/git/config`，用户第二配置文件，对应选项 `--global`。如果不明白这个文件的作用，跳过即可。
1. `~/.gitconfig` 用户配置文件，也称为 "global" 配置文件，对应选项 `--global`。
1. `$GIT_DIR/config`，repo 配置文件，对应选项 `--local`。

git 依次读取上面文件，后面的覆盖前面的。命令行选项 `-c <name>=<value>` 可以覆盖某个配置。

在安装 Git 之后，通常设置全局的用户名字和账户

```shell
git config --global user.name "Ivan Yan"
git config --global user.email "yan@gmail.com"
```

在写入选项时，默认使用 `--local`，即写入 repo 配置文件。这里是设置**全局**配置，因此要指定 `--global`。

## SSH


[SSH](../../github/git.md)

## Git Aliases

设置别名。这里别名是在 Git 下使用，`git <alias>`，不是 shell 别名。

```sh
git config --global alias.co checkout
git config --global alias.br branch
git config --global alias.ci commit
git config --global alias.st status

# 列出全部别名，`!` 使用外部命令
git config --global alias.la "!git config -l | grep alias | cut -c 7-"
```

- [Pro Git: Git Aliases](http://git-scm.com/book/en/v2/Git-Basics-Git-Aliases)
- [示例](<https://github.com/durdn/cfg/blob/master/.gitconfig)
