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
│   ├── page/
│   │   └── single.html         # Static pages (About, year archives, etc.)
│   ├── _default/
│   │   ├── single.html         # Individual blog post pages
│   │   └── list.html           # Archive listing page (categories, etc.)
│   └── partials/
│       ├── head.html           # <head> tag — meta, CSS, IndieWeb links
│       ├── header.html         # Site header — logo and nav
│       ├── sidebar.html        # Right rail — About, Currently, Link Box, Picture Box, Archives
│       ├── archives-content.html  # By Date + By Topic content for /archives/ page
│       └── footer.html         # Site footer
└── static/
    └── css/
        └── style.css           # All styles
```

---

## Making Changes

### Important: How Micro.blog uses this repo

Micro.blog cloned this repo once when the theme was created and keeps its **own internal copy** of the files. Pushing to GitHub does **not** automatically update what Micro.blog builds from. You need to update files in two places:

**1. Update Micro.blog (required for changes to go live):**
- Go to **Micro.blog → Design → Open Theme: Bump 2003 Redux**
- Click the file you want to edit in the left sidebar
- Paste in the updated content and click **Update Template**
- Then go back to **Design** and click **Update Design** to rebuild the site

**2. Keep GitHub in sync (recommended, for backup and version history):**
```bash
cd ~/Documents/bump-net-theme-26
git add .
git commit -m "Brief description of what you changed"
git push origin main
```

For small frequent changes like the blogroll or Currently box, you can skip BBEdit/GitHub entirely and just edit directly in the Micro.blog theme editor — it's faster.

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
| Archives By Date / By Topic lists | `layouts/partials/archives-content.html` |

---

## Year Archive Pages

Year archive pages live at `/archives/YEAR/` (e.g. `bump.net/archives/2023/`) and are regular Micro.blog pages — not Hugo taxonomy pages.

### How they work

`layouts/page/single.html` checks the page's URL. If it matches `/archives/YYYY/`, it filters all posts to that year and displays them grouped by month in chronological order. Otherwise it renders normal page content.

### Adding a new year

When a new calendar year starts, create a new page in Micro.blog:

1. Go to **Posts → Pages → New Page**
2. Set **Title** to the year (e.g. `2027`)
3. Set **Slug** to `archives/2027`
4. Leave the body blank
5. Click **Save**

No template changes needed — the template detects the URL automatically.

### Updating the sidebar cutoff year

The sidebar shows individual months for recent years and a single year link for older ones. The cutoff is controlled by `$cutoffYear` in `layouts/partials/sidebar.html` and `layouts/partials/archives-content.html`. Update both when you want to change the threshold.

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
