# gitattributes

```
git help gitattributes
```

gitattributes 控制文件的属性，通常是用于统一 eol。跟 gitignore 相比

- 一样分为 local, global 等层次
- pattern 一样，不过不能使用 negative patterns。

## eol

文本文件行结束符（eol, endings of line)，在跨平台工作时如何保持一致？

core.eol, 当 core.autocrlf 为 false 时，这个选项设置工作目录中文件的行结束符。有三个值：lf, crlf 和 native，默认值为 native，即跟操作系统一致，Windows 使用 CRLF，Linux 和 MacOS 使用 LF。

core.autocrlf 为 true 时，相当于 `* text=auto` 和 `core.eol=crlf`（即覆盖 core.eol），工作目录使用 CRLF，仓库使用 LF。

在 gitattributes 文件中 `* text=auto` 将所有文件视为 text，在签入签出文件时统一 eol。在上面两个选项为默认值的情况下，eol 跟操作系统一致。

```
* text=auto
*.vcproj text eol=crlf
*.jpg binary
```

`*.jpg binary` 即 `*.jpg -text -diff`。 diff 见帮助 "Generating diff text" 一节。

## 资料

- [Dealing with line endings](https://help.github.com/articles/dealing-with-line-endings/)
