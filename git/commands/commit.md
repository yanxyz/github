# Git commit

#### --message

`--message` 指定提交消息，不然 git 会打开编辑器，等待输入提交消息。

多个 `--message` 会合并为一个多段落消息。

```sh
git commit -am 'Fix a type'
```

`-a` 自动添加修改过的文件，不包含新建文件，新建文件要用 add 添加。

`git add -A`
添加当前目录下 changes

`git rm --cached <file>`
从 index 中删除文件。
