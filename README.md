# bump-net-theme-26

Custom Hugo theme for [bump.net](https://bump.net), hosted on [Micro.blog](https://micro.blog). A 2025 revival of the original 2003 bump.net design — dark background, lime green accents, two-column layout with sidebar.

---

## Repo Structure

```
bump-net-theme-26/
├── theme.toml                  # Theme metadata (name, Hugo min version)
├── config.json                 # Site params (tagline, since_year)
├── layouts/
│   ├── index.html              # Homepage (Log Box + sidebar)
│   ├── _default/
│   │   ├── single.html         # Individual blog post pages
│   │   ├── list.html           # Archive listing page
│   │   └── page.html           # Static pages (About, etc.)
│   └── partials/
│       ├── head.html           # <head> tag — meta, CSS, IndieWeb links
│       ├── header.html         # Site header — logo and nav
│       ├── sidebar.html        # Right rail — About, Currently, Link Box, Picture Box, Archives
│       └── footer.html         # Site footer
└── static/
    └── css/
        └── style.css           # All styles
```

---

## Making Changes

After editing any file in BBEdit, open Terminal and run:

```bash
cd ~/Documents/bump-net-theme-26
git add .
git commit -m "Brief description of what you changed"
git push origin main
```

Then go to **Micro.blog → Design → Update Design** to trigger a rebuild.

---

## Things You'll Edit Most Often

| What | File |
|---|---|
| Blogroll links | `layouts/partials/sidebar.html` |
| Currently box (reading, notebook, listening) | `layouts/partials/sidebar.html` |
| Nav links | `layouts/partials/header.html` |
| Footer text | `layouts/partials/footer.html` |
| Site tagline / since year | `config.json` |
| Any visual styles | `static/css/style.css` |

---

## Setting Up on a New Mac

**1. Check Git is installed:**
```bash
git --version
```
If not installed, macOS will prompt you to install it.

**2. Clone the repo:**
```bash
cd ~/Documents
git clone https://github.com/bump/bump-net-theme-26.git
```
Use your GitHub username and personal access token as the password.

**3. Open in BBEdit:**
```bash
open -a BBEdit ~/Documents/bump-net-theme-26
```

**Personal access token:** Tokens are tied to your GitHub account, not your machine. If yours has expired, generate a new one at [github.com/settings/tokens](https://github.com/settings/tokens) — set Contents permission to Read and write.

---

## Micro.blog Connection

The theme is registered in Micro.blog as **Bump 2003 Redux**, linked to this repo (`bump/bump-net-theme-26`). Hugo version is set to **0.91**.

To apply changes after pushing: **Micro.blog → Design → Update Design**.

You do not need to reclone the theme in Micro.blog unless the repo URL changes.

---

## Design Reference

Original 2003 bump.net color palette (extracted from source CSS):

| Element | Color |
|---|---|
| Body background | `#5a5a5a` |
| Panel background | `#0a0a0a` |
| Lime green (dates, links, accents) | `#66cc33` |
| Body text | `#cccccc` |
| Header background | `#2e2e2e` |
| Muted text / timestamps | `#888888` |