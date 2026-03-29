# JBook Step-by-Step Guide

This is a beginner-friendly guide for people who want to publish their own blog with GitHub Pages or Cloudflare Pages.

## What is this

`JBook` is a lightweight blog template.

You write plain Markdown files, push them to GitHub, and the project turns them into blog posts automatically. It supports:

- GitHub Pages
- Cloudflare Pages

If you prefer owning your content instead of depending on centralized publishing platforms, this setup is a practical option.

## The idea in one minute

What you actually need to do is simple:

1. Copy this repository.
2. Rename and adjust the site settings for yourself.
3. Write Markdown files in `thoughts/`.
4. Push to GitHub.
5. Publish with GitHub Pages or Cloudflare Pages.

## GitHub Pages

GitHub Pages is the easiest option if you want to get online quickly.

Basic flow:

1. Push the repository to your own GitHub account.
2. Open `Settings > Pages`.
3. Set `Source` to `GitHub Actions`.
4. Wait for the workflow to deploy your site.

If your repository is named `jbook`, the project site URL is usually:

`https://<your-username>.github.io/jbook/`

If you rename the repository, remember to update `baseurl` in [`_config.yml`](../_config.yml).

## Cloudflare Pages

Cloudflare Pages is better if:

- you want to bind your own domain
- you want more stable access in your region
- you do not want to use the GitHub Pages project-path style URL

Using your own domain is recommended.

![Cloudflare Step 1](https://github.com/user-attachments/assets/83ba8f18-c2be-4cd3-8653-3407586a240d)

Then continue:

![Cloudflare Step 2](https://github.com/user-attachments/assets/a9cf399a-7300-4de2-abe0-97e77cdd396e)

Choose this:

![Cloudflare Step 3](https://github.com/user-attachments/assets/7c4cd322-2851-41cb-9dd0-e6db0c91d4e5)

Then connect your repository to Cloudflare and locate the repo:

![Cloudflare Step 4](https://github.com/user-attachments/assets/14fe6d01-cd3c-474a-82df-223191336589)

Then follow the UI like this:

![Cloudflare Step 5](https://github.com/user-attachments/assets/77b9f120-40ab-4d83-b23e-281121945bce)

Use this build command:

```bash
python scripts/generate_posts.py && bundle exec jekyll build --config _config.yml,_config.cloudflare.yml
```

After that it should look roughly like this:

![Cloudflare Step 6](https://github.com/user-attachments/assets/faaeeb07-3585-4585-8c7b-e77fce71acde)

Continue until the build finishes:

![Cloudflare Step 7](https://github.com/user-attachments/assets/21adb15e-14ec-4ac9-8fe6-b0979cb8a245)

Continue again.

If you already have a domain, choose it there. If not, you can add one later.

![Cloudflare Step 8](https://github.com/user-attachments/assets/8404d328-03e4-4df6-a414-76ec068fa464)

You will then see something like:

![Cloudflare Step 9](https://github.com/user-attachments/assets/34cc72d4-3886-4dd2-9a56-0bc728029aa6)

Open the production link on the right side:

![Cloudflare Step 10](https://github.com/user-attachments/assets/46b7fd1b-5565-452b-a16a-0d1d3905274a)

Your site is now online.

## Domain note

Depending on your region, having your own domain may be much more convenient.

After binding a domain, you can configure a custom domain in the Pages dashboard. For example, if your domain is `devsan.fun`, your blog could be `blog.devsan.fun`.

But if this is only for personal use, check the renewal price carefully. Some domains are cheap for the first year and much more expensive later.

## Why this project exists

Centralized platforms usually have too much control:

- they can limit your reach
- they can suspend your account
- they can insert ads into your content
- and they may still give you little or no return

So this template exists to make self-publishing simpler. You can fork or copy it, rename it, and build your own blog.

If Cloudflare works better than GitHub Pages in your network environment, you can publish there directly.

AI tools helped polish this project, especially the part that made GitHub Pages and Cloudflare Pages work cleanly with different path rules.

## Daily usage

For normal use, you only need to:

1. create a `.md` file in `thoughts/`
2. put the title on the first line
3. leave one blank line and write the body
4. commit and push

The site updates automatically.

If you like the project, give the repository a star.
