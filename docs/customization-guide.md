# Customization Guide

A complete walkthrough of every change you need to make to turn this template into your personal website.

## Step 1: Edit `_config.yml` (required)

This is the **only file you must edit**. Open it in any text editor.

### Your identity

Change these two lines to your name:

```yaml
# Before:
title: "Your Name"
author: "Your Name"

# After (example):
title: "Jane Smith"
author: "Jane Smith"
```

- `title` — shown in the browser tab, site header, and SEO metadata
- `author` — shown in the footer

### Your social links

Uncomment (remove the `#`) the networks you use and fill in your details:

```yaml
# Before:
social-network-links:
#  email: "your@email.com"
#  github: yourusername
#  linkedin: yourusername

# After (example):
social-network-links:
  email: "jane@example.com"
  github: janesmith
  linkedin: janesmith
#  twitter: yourusername          ← leave commented if you don't use it
```

These links appear as icons in the site footer. Available networks: email, github, twitter, linkedin, instagram, google-scholar, orcid, youtube, medium, mastodon, calendly.

### SEO keywords

Replace with keywords relevant to you:

```yaml
# Before:
keywords: "personal website, blog"

# After (example):
keywords: "Jane Smith, software engineer, machine learning, blog"
```

### Timezone

Change to your local timezone ([list of timezones](https://en.wikipedia.org/wiki/List_of_tz_database_time_zones)):

```yaml
# Before:
timezone: "America/New_York"

# After (example):
timezone: "Europe/London"
```

## Step 2: Edit your pages

### Homepage — `index.html`

Replace the placeholder text with your own introduction:

```yaml
---
layout: home
title: Jane Smith
subtitle: Software Engineer & ML Researcher
---

Hi, I'm Jane! I build machine learning systems at Acme Corp.
Welcome to my personal site where I write about tech and research.
```

- `title` — your name (shown as the page heading)
- `subtitle` — a short tagline (shown below your name)
- Everything below `---` is your homepage content (Markdown or HTML)
- Blog posts will automatically appear below your content

### About page — `about.html`

Replace with your bio:

```yaml
---
layout: page
title: About
subtitle: A little about me
---

I'm a software engineer with 5 years of experience in...
```

### Contact page — `contact.html`

Add your actual contact details:

```html
---
layout: page
title: Contact
---

<div class="contact-info">
    <p>
        Email: <a href="mailto:jane@example.com">jane@example.com</a><br/>
        <a href="https://github.com/janesmith">GitHub</a> |
        <a href="https://linkedin.com/in/janesmith">LinkedIn</a>
    </p>

    <h3>Office</h3>
    <p>Building 5, Room 301<br/>Acme Corp, San Francisco, CA</p>
</div>
```

## Step 3: Add a profile photo (optional)

1. Place your photo in `assets/img/` (e.g. `assets/img/profile.jpg`)
2. Uncomment and update the avatar line in `_config.yml`:

```yaml
# Before:
# avatar: "/assets/img/avatar-icon.png"

# After:
avatar: "/assets/img/profile.jpg"
```

To make it circular, also uncomment:

```yaml
round-avatar: true
```

## Step 4: Add navigation pages (optional)

To add a new page (e.g. "Projects"):

1. Create `projects.md` in the root directory:

```yaml
---
layout: page
title: Projects
---

### Project A
Description of project A...

### Project B
Description of project B...
```

2. Add it to the navbar in `_config.yml`:

```yaml
navbar-links:
  Home: "index"
  About: "about"
  Projects: "projects"        # ← add this line
  Contact: "contact"
```

To remove a page, delete its line from `navbar-links`.

### Dropdown menus

You can group links under a dropdown:

```yaml
navbar-links:
  Home: "index"
  About: "about"
  More:                        # ← dropdown menu
    - Projects: "projects"
    - Publications: "publications"
  Contact: "contact"
```

## Step 5: Write blog posts (optional)

Create a file in `_posts/` named `YYYY-MM-DD-your-title.md`:

```yaml
---
layout: post
title: My First Real Post
subtitle: What I learned this week
tags: [learning, tech]
comments: true
---

Write your post content here in Markdown.

## You can use headings

And **bold**, *italic*, `code`, [links](https://example.com), images, etc.
```

### Post options

All fields except `layout` and `title` are optional:

| Field | What it does | Example |
|-------|-------------|---------|
| `subtitle` | Shown below the title | `"A deep dive into..."` |
| `tags` | Categorize the post | `[python, tutorial]` |
| `comments` | Enable comments section | `true` |
| `cover-img` | Large banner image at top | `"/assets/img/banner.jpg"` |
| `thumbnail-img` | Small image in blog feed | `"/assets/img/thumb.jpg"` |
| `share-img` | Image used for social sharing | `"/assets/img/share.jpg"` |
| `social-share` | Show share buttons | `true` |

## Step 6: Customize colours (optional)

Change the colour scheme in `_config.yml`. Any valid CSS colour works (`#hex`, `rgb()`, or colour names):

```yaml
# Default (light grey navbar, blue links):
navbar-col: "#EAEAEA"
link-col: "#008AFF"
hover-col: "#0085A1"

# Dark theme example:
navbar-col: "#1a1a2e"
navbar-text-col: "#e0e0e0"
page-col: "#16213e"
text-col: "#e0e0e0"
link-col: "#4fc3f7"
hover-col: "#81d4fa"
footer-col: "#1a1a2e"
footer-text-col: "#a0a0a0"
footer-link-col: "#4fc3f7"
```

## Step 7: Enable analytics (optional)

### Google Analytics

1. Create a property at [analytics.google.com](https://analytics.google.com)
2. Copy your Measurement ID (starts with `G-`)
3. Uncomment and fill in `_config.yml`:

```yaml
gtag: "G-XXXXXXXXXX"
```

### Google Tag Manager

```yaml
gtm: "GTM-XXXXXXX"
```

## Step 8: Enable comments (optional)

### Utterances (recommended — uses GitHub Issues)

1. Install the [Utterances app](https://github.com/apps/utterances) on your repo
2. Enable Issues in your repo settings
3. Uncomment in `_config.yml`:

```yaml
utterances:
  repository: "yourusername/yourusername.github.io"
  issue-term: title
  theme: github-light
  label: blog-comments
```

### Disqus

1. Sign up at [disqus.com](https://disqus.com)
2. Create a site and note your shortname
3. Uncomment in `_config.yml`:

```yaml
disqus: "your-shortname"
```

## Step 9: Deploy

### GitHub Pages (recommended)

1. Push your changes to GitHub
2. Go to **Settings → Pages → Build and deployment → Source**
3. Select **GitHub Actions**
4. Your site will be live at `https://yourusername.github.io` within a few minutes

### Custom domain (optional)

1. In your repo, go to **Settings → Pages → Custom domain**
2. Enter your domain (e.g. `www.janesmith.com`)
3. Add a `CNAME` file to your repo root containing just your domain:

```
www.janesmith.com
```

4. At your DNS provider, add a CNAME record pointing to `yourusername.github.io`

## Quick reference: files to change

| File | What to change | Required? |
|------|---------------|-----------|
| `_config.yml` | Name, social links, keywords, timezone | Yes |
| `index.html` | Homepage title, subtitle, and content | Yes |
| `about.html` | Your bio / about text | Yes |
| `contact.html` | Your contact details | Yes |
| `assets/img/` | Add your profile photo | Optional |
| `_posts/*.md` | Add blog posts | Optional |
