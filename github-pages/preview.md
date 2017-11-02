# 本地预览

以本项目为例。

## 安装

事先安装 Ruby 和 Bundler，[安装教程](/note/ruby/)。
一些 Gems 需要编译安装，Windows 在安装 Ruby 后务必安装 msys2。

在项目根目录创建一个文件 `Gemfile`

```Gemfile
source 'https://rubygems.org'
gem 'github-pages', group: :jekyll_plugins
gem 'wdm', '>= 0.1.0' if Gem.win_platform?
```

'wdm' 是为了解决在 Windows 下监视文件时 CPU 过高的问题。 需要
运行

```sh
$ bundle install
```

## 预览

如果不是刚完成安装，建议先更新 gems，以便与 GitHub Pages 保持一致

```sh
$ bundle update
$ gem clean # 清理旧 gems
```

运行

```sh
$ bundle exec jekyll serve --config _config.yml,_config-preview.yml
```

两个配置文件，`_config.yml` 供 github pages 使用；
`_config-preview.yml` 专用于本地预览。

## 问题

### Windows 安装失败

```
Installing commonmarker 0.17.6 with native extensions
checking for cmake... no
```

打开 Msys shell, 运行

```sh
# 搜索 cmake
$ pacman -Ss cmake

# 安装 cmake
# Windows x64 安装 mingw64 版本
$ pacman -S mingw64/mingw-w64-x86_64-cmake
```

### Windows 运行失败

> Dependency Error: Yikes! It looks like you don't have jekyll-remote-theme or one of its dependencies installed. In order to use Jekyll as currently configured, you'll need to install this gem. The full error message from Ruby is: 'Could not open library 'libcurl': 找不到指定的模块。 . Could not open library 'libcurl.dll': 找不到指定的模块。 . Could not open library 'libcurl.so.4': 找不到指定的模块。 . Could not open library 'libcurl.so.4.dll': 找不到指定的模块。 ' If you run into trouble, you can find helpful resources at https://jekyllrb.com/help/!

原因是找不到 libcurl.dll。解决办法是下载它。

第一种途径是从 curl 官网[下载](https://curl.haxx.se/download.html#Win32)。
可以用 Marc Hörsken 编译的。下载相应的压缩包，将压缩包内的 `lib/.libs/libcurl-4.dll` 复制到 PATH 某个目录，比如复制为 `/path/to/ruby/bin/libcurl.dll`。注意这里将 dll 名字为 libcurl.dll。

第二种途径是使用 msys2/mingw64 的。打开 Msys shell, 运行

```sh
$ pacman -Ss curl
# Windows x64 安装 mingw64 版本
$ pacman -S mingw64/mingw-w64-x86_64-curl
$ cp /mingw64/bin/libcurl-4.dll /path/to/ruby/bin/libcurl.dll
```

## 资料

[Setting up your GitHub Pages site locally with Jekyll - User Documentation](https://help.github.com/articles/setting-up-your-github-pages-site-locally-with-jekyll/#keeping-your-site-up-to-date-with-the-github-pages-gem)
