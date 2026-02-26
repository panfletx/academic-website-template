# Academic Website Template

Hugo-based academic website with Sveltia CMS for non-technical content editing.

**Live site:** https://panfletx.github.io/persona-template/
**Admin panel:** https://panfletx.github.io/persona-template/admin/
**User editing guide:** [EDITING-GUIDE.md](EDITING-GUIDE.md)

---

## Developer Setup

### Prerequisites
- [Hugo](https://gohugo.io/installation/) (extended version recommended)
- A GitHub account with access to `panfletx/persona-template`

### Local development

```bash
git clone https://github.com/panfletx/persona-template.git
cd website
hugo server
```

Visit `http://localhost:1313` to preview the site.

---

## CMS Authentication Setup (one-time)

The CMS uses GitHub OAuth via a Cloudflare Worker. This only needs to be configured once.

### 1. Deploy the auth worker

Deploy [`sveltia/sveltia-cms-auth`](https://github.com/sveltia/sveltia-cms-auth) to Cloudflare Workers (free tier: 100k requests/day).

### 2. Register a GitHub OAuth App

1. Go to GitHub → Settings → Developer settings → OAuth Apps → New OAuth App
2. Set:
   - **Application name:** Website CMS
   - **Homepage URL:** `https://panfletx.github.io/persona-template/`
   - **Authorization callback URL:** `https://sveltia-cms-auth.WORKER_NAME.workers.dev/callback`
3. Note the **Client ID** and generate a **Client Secret**

### 3. Configure the worker

Set these environment variables in the Cloudflare Worker dashboard:
- `GITHUB_CLIENT_ID` — from step 2
- `GITHUB_CLIENT_SECRET` — from step 2
- `ALLOWED_DOMAINS` — `panfletx.github.io`

### 4. Update the CMS config

In [`static/admin/config.yml`](static/admin/config.yml), replace `WORKER_NAME` with your actual worker subdomain:

```yaml
base_url: https://sveltia-cms-auth.WORKER_NAME.workers.dev
```

---

## Project Structure

```
content/          # Page content (Markdown)
  _index.md       # About page (bio)
  research.md
  teaching.md
  creative-writing.md
  cv/_index.md
data/
  identity.yaml   # Name, title, email, photo — edit here or via CMS
  cv.yaml         # CV data — edit here or via CMS
layouts/
  index.html      # Base HTML template
  partials/
    left-column.html  # Sidebar (photo, name, mobile nav)
    sidenav.html      # Desktop navigation
static/
  admin/          # Sveltia CMS
    index.html
    config.yml
  uploads/        # Images uploaded via CMS
  css/
    main.css
```

## Adding a Page (Developer)

1. Create `content/PAGENAME.md` with menu front matter:
   ```yaml
   ---
   title: "Page Title"
   menu:
     main:
       weight: 6
       name: Page Title
   ---
   ```
2. Hugo auto-generates the route and adds it to the nav.
3. Add the page to the `pages` collection in `static/admin/config.yml` if needed.
