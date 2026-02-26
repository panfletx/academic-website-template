# Editing Your Website

This guide explains how to update your website without writing any code. Everything is done through a form-based editor in your browser.

---

## Getting Started

1. Go to **`https://panfletx.github.io/persona-template/admin/`**
2. Click **"Login with GitHub"**
3. Authorize the app if prompted — you only need to do this once
4. You'll see the Content Manager with everything you can edit listed on the left

---

## Updating Your Name, Title, or Photo

1. In the left sidebar, click **"Site Identity"**
2. Click **"Name, Title & Photo"**
3. Edit any of the fields:
   - **Full Name** — your name as it appears on the site
   - **Position / Title** — your role/institution
   - **Email Address** — shown in your profile
   - **Profile Photo** — click "Choose an image" to upload a new headshot (JPG or PNG)
4. Click **"Save"** in the top right

Your site will rebuild in about 2–3 minutes.

---

## Editing Your Bio (About Page)

1. Click **"About Page"** in the left sidebar
2. Click **"About (Bio)"**
3. Edit the **Bio** field — it works like a simple word processor:
   - Use the toolbar to make text **bold**, *italic*, or add links
   - Press Enter for a new paragraph
4. Click **"Save"**

---

## Editing Research, Teaching, or Creative Writing Pages

1. Click **"Content Pages"** in the left sidebar
2. Click the page you want to edit (Research, Teaching, or Creative Writing)
3. Edit the **Body** field — the rich text editor works like Word or Google Docs
4. Click **"Save"**

---

## Adding a New Page

1. Click **"Content Pages"** in the left sidebar
2. Click the **"New Content Pages"** button (top right)
3. Fill in:
   - **Title** — the page heading
   - **Nav Label** — what appears in the navigation menu
   - **Nav Weight** — the order in the menu (e.g., `6` puts it after CV)
   - **Body** — the page content
4. Click **"Save"**

The new page will appear in the navigation automatically.

---

## Editing Your CV

1. Click **"CV"** in the left sidebar
2. Click **"CV Sections"**
3. You'll see a list of sections (Education, Publications, Teaching, etc.)
4. To **edit an entry**: click on the section, then click the entry and change the fields
5. To **add an entry**: click a section, then click **"Add entry"** at the bottom of the entries list
6. To **add a new section**: click **"Add sections"** at the bottom of the sections list
7. Click **"Save"** when done

**Fields available for each CV entry:**
- **Title / Role** — position name, paper title, etc.
- **Institution** — university or organization
- **Location** — city, state/country
- **Years** — e.g., `2022–Present`
- **Note** — additional description (thesis title, course names, etc.)
- **Text** — for publications, use this field for the full citation

---

## What Happens After I Save?

When you save any change, it is committed to GitHub and your site automatically rebuilds. This takes **2–3 minutes**. After that, visit your site and refresh the page to see the changes.

---

## Troubleshooting

**Changes aren't showing up**
Wait 3 minutes and do a hard refresh (Ctrl+Shift+R on Windows/Linux, Cmd+Shift+R on Mac). If still not showing, check the GitHub repository's "Actions" tab to see if the build succeeded.

**I accidentally deleted something**
Every save is stored in your git history. Contact your developer — deleted content can always be recovered.

**I'm getting a login error**
Make sure you are logging in with the GitHub account that has access to the `panfletx/website` repository. If the problem persists, contact your developer.
