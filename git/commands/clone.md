# Git clone

git URLs 见 `git help fetch`

### 如何只 clone 一个分支？

```shell
a=file:///f/code/a
git clone $a b1
git clone $a b2 --branch develop
git clone $a b3 --branch develop --single-branch
git clone $a b4 --branch develop --depth=1
```

```sh
git clone -h
git clone -b
```


