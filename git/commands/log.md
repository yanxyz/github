# Git log

`git log`
列出全部 commits，以 less 的模式浏览，q 键退出。

`git log -2`
最近两次 commits

`git log --pretty=oneline`
单行

`git log -S function_name`
只显示匹配 string 的 commits

`git log --since=2.weeks`
最近两周 commits

`git log --author="Ivan Yan"`
某人提交的 commits

## 资料

- [Pro Git: Viewing the Commit History](https://git-scm.com/book/en/v2/Git-Basics-Viewing-the-Commit-History)
