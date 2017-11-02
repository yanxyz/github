# Git tag

查看 tags

```sh
git tag # list all tags
git tag -l "v1.8.5*" # list some tags
```

tag types:

- lightweight tags 是 commit 的 pointer
- annotated tags 以 full objects 保存在 Git 中，包含 email, date 等信息。

创建 annotated tag，使用 `-a`, `-m` 等 options；创建 lightweight tags 不使用这些 options。

```sh
git tag -a v1.4 -m "version 1.4" # last commit
git show v1.4

git tag -a v1.5 9fceb02  # old commit
```

推送到远程服务器

```sh
git push origin v1.5
git push origin --tags # 推送所有的 tags
```

删除远程 tag

```sh
git push origin :v1.5
git push origin --delete tag v1.5
```

签出 tag，不能实际签出，以分支的形式签出

```sh
git checkout -b version1.5 v1.5
```

## 资料

- [Pro Git: Tagging](https://git-scm.com/book/en/v2/Git-Basics-Tagging)
