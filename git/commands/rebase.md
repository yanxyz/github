# Git rebase

Git 有两种合并 branch 的方法：merge, rebase。

rebase，将 current branch 与 target branch 的变化在 current branch 生成新的 commit

```sh
git checkout experiment
git rebase master
```

![](https://git-scm.com/book/en/v2/images/basic-rebase-3.png)

现在 target branch 可以 fast-forward merge

```sh
git checkout master
git merge master
```

![](https://git-scm.com/book/en/v2/images/basic-rebase-3.png)

可以看到 target branch 的历史是线性的。


## 资料

- [Pro Git: Rebasing](https://git-scm.com/book/en/v2/Git-Basics-Tagging)

