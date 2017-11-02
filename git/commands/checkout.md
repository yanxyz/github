# git checkout

## 分支

`git checkout <branch>`

切换分支。如果本地没有 `<branch>` 而远程有，则相当于

```sh
git checkout -b <branch> --track <remote>/<branch>
```

- `-b`，如果分支不存在，则创建此分支。
- `-f`，强制切换，扔掉 working tree 的修改。


## 文件

`git checkout -- README.md`
签出 README.md，`--` 表示停止解析选项。选项 `-f` 强制签出扔掉 working tree 的修改。

`git checkout -f -- *`
强制签出所有的文件。
