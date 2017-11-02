# Kramdown

Github pages 使用的 markdown 引擎为 kramdown，语法高亮引擎为 Rouge

[GitHub Pages now faster and simpler with Jekyll 3.0](https://github.com/blog/2100-github-pages-now-faster-and-simpler-with-jekyll-3-0)

注意，Github pages 和 github.com 并不完全一样。

## 配置

[Options](https://kramdown.gettalong.org/options.html)


## 问题

### 自动链接

Github pages 自动链接要放到 `<>` 里

```
{% raw %}
<https://pages.github.com/themes/>
{% endraw %}
```

## HTML

解析 HTML tags 里的 markdown, github.com 支持。
kramdown 也支持，`parse_block_html`。
不过默认是关闭的。

修改 jekyll 配置

```yaml
kramdown:
  parse_block_html: true
```

一个应用案例是使用 Primer 的 grid

```html
<section class="columns">
  <div class="column one-half">

<!-- markdown -->

  </div>

  <div class="column one-half">

<!-- markdown -->

  </div>
</section>
```

### `<details>` tag

- <https://github.com/gettalong/kramdown/issues/155>

### TOC

[doc](https://kramdown.gettalong.org/converter/html.html#toc)

[Table of contents using Jekyll and Kramdown - Stack Overflow](https://stackoverflow.com/questions/38417624/)

#### Options

`toc_levels` 目前只有 site level, 没有 page level

`_config.yml`

```yaml
kramdown:
  toc_levels: "2,3,4" # "2..4" 无效
```

## 资料

- [Markdown Kramdown Tips & Tricks](https://about.gitlab.com/2016/07/19/markdown-kramdown-tips-and-tricks/)
