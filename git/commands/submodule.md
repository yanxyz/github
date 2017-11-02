# git submodule

子模块与主项目是两个不同的库。主项目下有一个文件  .gitmodules，记录了子模块的信息。当在子模块提交修改后，主项目也要做一次提交，以更新  子模块信息，其它引用此模块的项目要拉取然后提交。

列出子模块
`git submodule`

添加子模块

```sh
git submodule add <repo>
git submodule init
```

更新 submodule 并推送到远程仓库

```sh
# 子模块提交修改
git add .
git commit -m
git push

# 回到主项目
git add -u
git commit -m
git push
```

其它引用了子模块的库
git pull
git submodule update

从远程仓库更新 submodule
# 拉取更新
git pull
# 查看 submodule 是否有更新
git status
# 如果有更新则更新。
git submodule update
这里的风险是忘了 git submodule update，然后提交时没有检查，直接 git commit -a， 这样将旧的 submodule 提交上去了。

如果引用 了较多子模块，显然不能一个个手工更新，使用如下命令
git submodule foreach git pull

http://josephjiang.com/entry.php?id=342
http://gitbook.liuhui998.com/5_10.html
http://bec-systems.com/site/1020/git-submodules-can-now-track-branches


```sh
# 签出主分支，相当于子模块提交了 commit
git checkout master
git push
#
git add -u
git commit -m
git push


签出子模块
git clone <repo>
这时子模块是空的
git submodule init
git submodule update

或者
git clone --recursive <repo>

## 删除 submodule

http://stackoverflow.com/questions/1260748/how-do-i-remove-a-git-submodule

oldPath="vendor/example"
git config -f .git/config --remove-section "submodule.${oldPath}" # Git v1.8.4 deinit
git config -f .gitmodules --remove-section "submodule.${oldPath}" # Git v1.8.5 不需要
git rm --cached "${oldPath}"
rm -rf "${oldPath}" ## remove src (optional)
rm -rf ".git/modules/${oldPath}" ## cleanup gitdir (optional housekeeping)
git add .gitmodules
git commit -m "Removed ${oldPath}"

