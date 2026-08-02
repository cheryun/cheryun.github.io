# 逆熵者

个人站。静态站点，无构建流程 —— 目录里是什么，线上就是什么。

## 结构

```
.
├── index.html          首页
├── writing.html        文章索引 + 碎片
├── style.css           全部样式（改颜色只动最上面的 :root）
├── posts/
│   ├── _template.html  复制它开新文章
│   └── hello.html      第一篇，同时是排版说明书
├── _headers            安全响应头（只在 Cloudflare Pages 生效）
├── .nojekyll           关掉 GitHub Pages 的 Jekyll 处理
└── .gitignore
```

## 加一篇文章

1. 复制 `posts/_template.html` → 改名，如 `posts/resistance.html`
2. 改 `<title>`、`<h1>`、日期，写正文
3. 回 `writing.html`，把对应条目的 `href` 指过去，删掉 `class` 里的 `is-draft`

第 3 步最容易忘 —— 忘了文章就存在但没入口。

## 发布

```
git add .
git commit -m "写了新的一篇"
git push
```

推上去 30 秒到 1 分钟后线上生效。

## 技术

语义化 HTML5 + 原生 CSS（自定义属性做设计令牌）+ 一段 vanilla JS。
零依赖、零第三方请求、无追踪脚本、无 cookie。
深浅色跟随系统 `prefers-color-scheme`。
