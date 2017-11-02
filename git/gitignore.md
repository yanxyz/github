# gitignore

```sh
git help gitignore
```

## gitignore file

gitignore patterns 有多个来源，优先级从高到低（同一优先级内后面的覆盖前面的）：

1. 命令行参数
1. 从当前文件所在目录开始向上一直到根目录查找 .gitignore 文件，离文件近的优先级高
1. `$GIT_DIR/info/exclude` 文件
1. `core.excludesFile` 指定的文件

通常在项目根目录下面放一份 `.gitignore` 文件，这个文件属于项目的一部分，所有克隆都会使用它。

`$GIT_DIR/info/exclude` 文件只针对这个本地库。

`core.excludesFile` 指定的文件针对本机上所有的项目，查看具体位置：

```sh
git config -l
git config --get core.excludesfile
```

建议将系统文件 patterns 添加到这个文件：

```
*.DS_Store
._*
Thumbs.db
.cache
```


### gitignore 不影响 tracked files

```sh
git rm --cached file
```


## gitignore pattern

`#` 开始的表示注释。

`\` 可以用于转义，比如 `\#`, `\!`。

`!` 开始的表示取消忽略。出于性能的考虑，如果文件的父目录被忽略，`!` 不能取消忽略此文件。

`/` 开始的表示是库根目录。其它的是相对路径，`.gitignore` 文件指定的是相对于此文件，其它指定的是相对于库根目录。

`foo/` 表示 foo 目录，而不是 foo 文件或链接。

`*` 不匹配 `/`, `foo/*.html` 只匹配 foo 目录下的文件，不会匹配 foo 子目录下的文件。

单独的 `**` 可以匹配 `/`。`**/foo.txt` 匹配所有目录下面的 foo.txt。`foo/**` 匹配 foo 目录及其子目录下的所有文件。

## 资料

- [Ignoring files](https://help.github.com/articles/ignoring-files)
- [常用的 gitignore](https://github.com/github/gitignore)
