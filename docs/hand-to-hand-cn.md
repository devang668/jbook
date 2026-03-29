# JBook 手把手中文教程

这是给中文用户准备的一份从零开始教程，适合第一次接触 GitHub Pages 或 Cloudflare Pages 的用户。

## 这是什么

`JBook` 是一个轻量博客模板。

你平时只需要写普通 Markdown，推送到仓库后，它会自动生成博客页面。它同时兼容：

- GitHub Pages
- Cloudflare Pages

如果你更喜欢自己掌控内容，而不是把内容发到中心化平台，这种方式会更稳。

## 快速理解

你要做的事情其实很简单：

1. 复制这个仓库。
2. 改成你自己的仓库名和站点信息。
3. 在 `thoughts/` 里写 Markdown。
4. 推送到 GitHub。
5. 用 GitHub Pages 或 Cloudflare Pages 发布。

## GitHub Pages

GitHub Pages 适合想快速上线的人。

大致流程：

1. 把仓库推送到你自己的 GitHub。
2. 进入仓库的 `Settings > Pages`。
3. `Source` 选择 `GitHub Actions`。
4. 等待 Actions 自动部署完成。

如果你的仓库名是 `jbook`，那项目页地址通常会是：

`https://<你的用户名>.github.io/jbook/`

如果你改了仓库名，就记得同步修改 [`_config.yml`](../_config.yml) 里的 `baseurl`。

## Cloudflare Pages

Cloudflare Pages 更适合这些情况：

- 你想绑自己的域名
- 你想让访问更稳定
- 你不想使用 GitHub Pages 的项目路径

最好绑定一个个人域名。

![Cloudflare 步骤 1](https://github.com/user-attachments/assets/83ba8f18-c2be-4cd3-8653-3407586a240d)

然后继续：

![Cloudflare 步骤 2](https://github.com/user-attachments/assets/a9cf399a-7300-4de2-abe0-97e77cdd396e)

看这里：

![Cloudflare 步骤 3](https://github.com/user-attachments/assets/7c4cd322-2851-41cb-9dd0-e6db0c91d4e5)

接着关联自己的仓库和 Cloudflare，并找到仓库位置：

![Cloudflare 步骤 4](https://github.com/user-attachments/assets/14fe6d01-cd3c-474a-82df-223191336589)

然后按图操作：

![Cloudflare 步骤 5](https://github.com/user-attachments/assets/77b9f120-40ab-4d83-b23e-281121945bce)

构建命令填写下面这条：

```bash
python scripts/generate_posts.py && bundle exec jekyll build --config _config.yml,_config.cloudflare.yml
```

完成后大概会是这样：

![Cloudflare 步骤 6](https://github.com/user-attachments/assets/faaeeb07-3585-4585-8c7b-e77fce71acde)

点击继续，看到构建完成：

![Cloudflare 步骤 7](https://github.com/user-attachments/assets/21adb15e-14ec-4ac9-8fe6-b0979cb8a245)

再继续。

如果有自己的域名，就选域名；没有的话，后面也可以补。点击继续。

![Cloudflare 步骤 8](https://github.com/user-attachments/assets/8404d328-03e4-4df6-a414-76ec068fa464)

你会看到：

![Cloudflare 步骤 9](https://github.com/user-attachments/assets/34cc72d4-3886-4dd2-9a56-0bc728029aa6)

点击生产环境右边的链接，就能打开站点：

![Cloudflare 步骤 10](https://github.com/user-attachments/assets/46b7fd1b-5565-452b-a16a-0d1d3905274a)

这样网站就上线了。

## 域名提示

因为部分地区网络环境的原因，你可能会更需要一个自己的域名。

绑定域名以后，可以在 Pages 项目里设置自定义域名。比如你的域名是 `devsan.fun`，博客就可以用 `blog.devsan.fun`。

但如果只是自用，一定要看清域名续费价格。不要只看第一年很便宜，有些域名第二年续费会非常高。

## 为什么做这个项目

中心化平台通常拥有很强的控制权：

- 它可以限流你的内容
- 可以封禁你的账号
- 可以在你的内容里插入广告
- 但未必会给你合理回报

所以做了这样一个博客模板。你把它 fork 或复制之后，改个名字，就可以拥有自己的博客。

如果你所在地区的网络环境更适合 Cloudflare，也可以直接部署到 Cloudflare Pages。

这个项目在完善过程中借助了 AI 工具，最关键的一步，是把 GitHub Pages 和 Cloudflare Pages 的路径兼容一起理顺了。

## 后面怎么用

平时只需要：

1. 在 `thoughts/` 目录里新建一个 `.md`
2. 第一行写标题
3. 空一行后写正文
4. 提交推送

站点就会自动更新。

如果你喜欢这个项目，可以给仓库点一个 star。
