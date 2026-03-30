# JBook


快速看见效果 https://devang668.github.io/jbook/

<img width="1888" height="1234" alt="image" src="https://github.com/user-attachments/assets/e39d0ca5-ca0c-49b1-9df1-b47052857eb8" />

部署需要花费时间？5分钟左右。

fork 

然后只需要设置的pages里设为开放（其实默认就是开放的，不用设置），然后settings/pages 勾选.
<img width="2062" height="993" alt="image" src="https://github.com/user-attachments/assets/455536bf-be40-4745-be6c-4634b8329041" />



这是啥呢？
---------------------
一个可公开分享的轻博客模板。

它基于 `Jekyll + Markdown + GitHub Pages`，同时兼容 `Cloudflare Pages`。平时只需要在 `thoughts/` 里写 Markdown，构建脚本会自动生成 `_posts`，并提供移动端优先的 PWA 外观。

## Tutorials

如果你更希望按图一步一步配置，可以直接看中文教程：

- [手把手中文教程](docs/hand-to-hand-cn.md)
- [Step-by-step English guide](docs/hand-to-hand-en.md)

## 特性

- 只写普通 Markdown，不用手写 `_posts/YYYY-MM-DD-title.md`
- 自动根据文件名或 git 历史推断发布日期
- GitHub Pages 自动部署
- Cloudflare Pages 兼容配置
- PWA 安装、离线缓存、移动端优化布局

## 写作方式

1. 在 `thoughts/` 里新建一个 `.md` 文件。
2. 第一行写标题。
3. 空一行后直接写正文。
4. 提交并推送，站点会自动更新。

示例：

```md
今天的小想法

这里直接写正文。
想贴链接、图片、代码块都可以。
```

## GitHub Pages

仓库推送到 `main` 后，进入 GitHub 仓库：

`Settings > Pages > Source > GitHub Actions`

项目页默认地址通常是：

`https://<owner>.github.io/jbook/`

如果你把仓库名改掉了，记得同步修改 [`_config.yml`](_config.yml) 里的 `baseurl`。

## Cloudflare Pages

如果你打算绑定自己的域名或使用 Cloudflare Pages，请使用下面这组配置：

- Production branch: `main`
- Framework preset: `Jekyll` 或 `None`
- Build command: `python scripts/generate_posts.py && bundle exec jekyll build --config _config.yml,_config.cloudflare.yml`
- Build output directory: `_site`

这样 GitHub Pages 仍然走仓库路径，Cloudflare Pages 则会走根路径。

## 需要改的配置

在开始正式写作前，建议先改这几个字段：

- [`_config.yml`](_config.yml) 里的 `title`
- [`_config.yml`](_config.yml) 里的 `description`
- [`_config.yml`](_config.yml) 里的 `url` / `baseurl`
- [`_config.yml`](_config.yml) 里的 `github.repository_url`
- [`_config.cloudflare.yml`](_config.cloudflare.yml) 里的 `url`

## 许可

默认附带 [MIT License](LICENSE)。

