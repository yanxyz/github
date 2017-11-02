# Git branch

- [切换分支 checkout](checkout.md)

```sh
git push -u origin master
```

推送当前分支到远程 master 分支


## 如何删除远程分支

```sh
git branch -d -r origin/html origin/man
```

删除两个远程分支（本地记录）。如果远程仓库存在这两个分支，下次 fetch 或 pull 仍然会创建它们。

那么怎样真正的删除远程分支？

```sh
git push origin --delete <branch>
# 旧版本 git
git push origin :<branch>
```

已删除的远程分支，其它机器上仍然可以看到

```sh
git branch -a
```

清理，两种方法

```sh
git pull -all --prune
git remote prune origin
```

## shell 如何获取当前分支的名字

```sh
git symbolic-ref --short HEAD
```

<http://stackoverflow.com/questions/6245570/how-to-get-the-current-branch-name-in-git>

## orphan 分支

[github `gh-pages` 分支](https://help.github.com/articles/creating-project-pages-using-the-command-line/)

## 其它

- <http://learngitbranching.js.org/>
