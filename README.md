# Whalefall Blog

Whalefall 的安全学习博客，记录 CTF、Pwn 与二进制安全相关内容。使用 [Jekyll](https://jekyllrb.com/) 构建，通过 GitHub Pages 原生托管。

## 目录结构

```text
.
├── _config.yml        # 站点配置
├── _posts/            # 文章（文件名格式：YYYY-MM-DD-标题.md）
├── assets/images/     # 文章图片
├── index.md           # 首页（文章列表）
├── about.md           # 关于页
├── Gemfile            # 本地预览依赖
└── LICENSE
```

## 本地预览

需要 Ruby 3.x 与 Bundler。

```bash
bundle install
bundle exec jekyll serve
```

浏览器访问 <http://127.0.0.1:4000/>。

## 写文章

在 `_posts/` 下新建 `YYYY-MM-DD-标题.md`，并添加 front matter：

```yaml
---
title: 文章标题
date: 2026-01-01 12:00:00
categories:
  - CTF解题
tags:
  - CTF
---
```

正文中的图片统一放在 `assets/images/`，使用 `relative_url` 引用，保证在本地和 GitHub Pages 上路径一致：

```markdown
![图片说明]({{ '/assets/images/example.png' | relative_url }})
```

## 部署

推送到 `main` 分支后，在仓库 **Settings → Pages** 中选择：

- Source：Deploy from a branch
- Branch：`main`
- Folder：`/ (root)`

GitHub Pages 会自动构建并发布。

> 本仓库命名为 `Whalefall-prog.github.io`，作为用户页发布，访问地址为 <https://whalefall-prog.github.io/>，`baseurl` 保持为空。若绑定自定义域名，请在仓库根目录添加 `CNAME` 文件，并保持 `baseurl` 为空。

## License

[MIT](LICENSE)
