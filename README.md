# Personal Website Template

A minimal, ready-to-use personal website template powered by [Jekyll](https://jekyllrb.com/) and [Beautiful Jekyll](https://beautifuljekyll.com/).

Deploy to GitHub Pages in minutes — no coding required.

## Quick Start

1. **Fork** this repository (or click "Use this template")
2. Rename the repo to `yourusername.github.io`
3. Edit `_config.yml` with your name, links, and preferences
4. Go to **Settings → Pages → Source** and select **GitHub Actions**
5. Your site will be live at `https://yourusername.github.io` within a few minutes

## Local Development

For detailed installation instructions (Git, Ruby, Jekyll, Bundler), see:

- [Setup guide for Windows](docs/setup-windows.md)
- [Setup guide for Linux / macOS](docs/setup-linux-macos.md)

**If you already have Ruby and Bundler installed:**

```bash
git clone https://github.com/ai-vnv/personal-website-template.git
cd personal-website-template
bundle install
bundle exec jekyll serve
```

Open [http://localhost:4000](http://localhost:4000) in your browser.

## Customization

For a **complete step-by-step walkthrough** of every change you need to make, see the **[Customization Guide](docs/customization-guide.md)**.

Quick summary — files you need to change:

| File | What to change | Required? |
|------|---------------|-----------|
| `_config.yml` | Name, social links, keywords, timezone | Yes |
| `index.html` | Homepage title, subtitle, and content | Yes |
| `about.html` | Your bio / about text | Yes |
| `contact.html` | Your contact details | Yes |
| `assets/img/` | Add your profile photo | Optional |
| `_posts/*.md` | Add blog posts | Optional |

## Features

- Responsive design (Bootstrap 4)
- Blog with tags, RSS feed, and pagination
- SEO optimized (Open Graph, Twitter Cards, sitemap)
- Google Analytics / Tag Manager / Matomo support
- Comments via Disqus or Utterances
- MathJax for LaTeX equations
- Syntax highlighting for code blocks
- Customizable colour scheme
- Automatic GitHub Pages deployment via GitHub Actions

## Directory Structure

```
├── _config.yml          # Site configuration (start here!)
├── index.html           # Homepage
├── about.html           # About page
├── contact.html         # Contact page
├── _posts/              # Blog posts
├── _layouts/            # Page templates
├── _includes/           # Reusable components
├── assets/css/          # Stylesheets
├── assets/js/           # JavaScript
├── assets/img/          # Images
└── .github/workflows/   # GitHub Actions CI/CD
```

## Credits

Based on [Beautiful Jekyll](https://beautifuljekyll.com/) v5.0.0 by [Dean Attali](https://deanattali.com/).

## License

MIT License — see [LICENSE](LICENSE) for details.
