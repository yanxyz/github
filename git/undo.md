# Git undo

已分享的 commits（自己推送的或者拉取别人的）不要动！

#### 放弃修改

```sh
git checkout -- <file>
git checkout -- * # 重新签出所有的文件
```

#### commit 之后发现 commit message 有拼写错误

```sh
git commit --amend
```

`--amend` 替换上次 commit。如果 index 没有 changes 则只修改 commit message。

#### commit 之后发现遗漏了文件

```sh
git add forgotten_file
git commit --amend --no-edit  # --no-edit 不修改 commit message
```

