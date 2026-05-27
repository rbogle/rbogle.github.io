# Setup Guide — rbogle.github.io

## Prerequisites

- [Hugo extended](https://gohugo.io/installation/) v0.147.0+ installed locally
- Git

## First-time setup

### 1. Create the GitHub repo

Create a new **public** repo at github.com/rbogle named exactly `rbogle.github.io`.

### 2. Clone and initialize

```bash
git clone https://github.com/rbogle/rbogle.github.io.git
cd rbogle.github.io
```

Copy all the files from this scaffold into the repo root.

### 3. Add the PaperMod theme

```bash
git submodule add --depth=1 https://github.com/adityatelange/hugo-PaperMod.git themes/PaperMod
git submodule update --init --recursive
```

### 4. Test locally

```bash
hugo server -D
```

Open http://localhost:1313 — you should see the site.

### 5. Push to GitHub

```bash
git add .
git commit -m "Initial site scaffold"
git push origin main
```

### 6. Enable GitHub Pages

In your repo settings:
- Go to **Settings → Pages**
- Source: **GitHub Actions**
- The deploy workflow will run automatically on push

### 7. Configure your custom domain

In **Settings → Pages → Custom domain**, enter `rianbogle.com`.

In your DNS provider (wherever rianbogle.com is registered), add these records:

```
# A records (GitHub Pages IPs)
@    A    185.199.108.153
@    A    185.199.109.153
@    A    185.199.110.153
@    A    185.199.111.153

# CNAME for www
www  CNAME  rbogle.github.io
```

DNS propagation takes up to 24 hours. GitHub will auto-provision an SSL certificate once it resolves.

---

## Writing a new post

```bash
hugo new posts/your-post-slug.md
```

This creates `content/posts/your-post-slug.md` from the archetype. Edit the frontmatter, set `draft: false` when ready, and push to publish.

## Cross-posting to Medium

1. Publish on rianbogle.com first (establishes canonical URL)
2. On Medium: New Story → Import from URL → paste your post URL
3. Medium will import the content and automatically set the canonical URL to your site

## LinkedIn checklist (on publish day)

- [ ] Post is live at rianbogle.com
- [ ] Cross-posted to Medium with canonical URL set
- [ ] Write amplification post: one sharp sentence from the article + link
- [ ] Schedule Dev.to cross-post (optional, for practitioner posts)
