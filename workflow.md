# Github 流程

## Create

打开 Github 页面，点击 导航栏上的 '+' 按钮，创建 repo。此时 repo 没有代码，Github 会给出代码提交教程，[示例](https://github.com/yanxyz/new-repository)。

## Fork

fork别人的库

- <https://help.github.com/articles/fork-a-repo>
- <https://github.com/MarkUsProject/Markus/wiki/Gitkeepingpace>

保持源项目的更新

```sh
git remote add upstream <url>
git fetch upstream
git checkout master
git merge upstream/master

如果正在分支上而源项目 master 更新了
git rebase upstream/master
```
