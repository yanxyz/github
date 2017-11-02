# git diff

`git diff`
working tree 与 index 的不同，即没有存入 index 的 changes。

`git diff --cached`
index 与上次 commit 的不同。

`git diff HEAD`
working tree 与上次 commit 的不同。

`git diff -- readme.md`
readme.md 文件，working tree 与 index 的不同。

`git diff HEAD^ HEAD`
上上次 commit 与上次 commit 的不同。

## git difftool

difftool 是 diff 前端命令，调用外部工具查看不同，可以使用 diff 的选项。

- [Beyond Compare](../../software/bcompare/index.md)
