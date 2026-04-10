# storint.org — Setup Guide

## Files in this folder

| File | What it is |
|------|-----------|
| index.html | Home page |
| toolkit.html | Toolkit page (PDF embed) |
| feedback.html | Feedback page (Google Form embed) |
| style.css | All shared styles |
| toolkit.pdf | ADD THIS — export from Canva |

---

## Step-by-step: Getting the site live

### Step 1 — Create a GitHub account
Go to https://github.com and sign up (free).

### Step 2 — Create a new repository
- Click the green "New" button
- Name it anything, e.g. `storint-website`
- Set it to **Public**
- Click "Create repository"

### Step 3 — Upload these files
- Click "uploading an existing file"
- Drag and drop ALL files from this folder (index.html, toolkit.html, feedback.html, style.css)
- Click "Commit changes"

### Step 4 — Enable GitHub Pages
- Go to your repo → Settings → Pages (left sidebar)
- Under "Source", select: **Deploy from a branch**
- Branch: **main**, folder: **/ (root)**
- Click Save
- GitHub will give you a URL like: https://yourusername.github.io/storint-website

### Step 5 — Point your Squarespace domain to GitHub Pages

In Squarespace:
- Domains → storint.org → DNS Settings
- Delete any existing A records
- Add these 4 A records (all pointing to @):
  - 185.199.108.153
  - 185.199.109.153
  - 185.199.110.153
  - 185.199.111.153
- Add 1 CNAME record:
  - Name: www
  - Value: yourusername.github.io

In GitHub:
- Repo → Settings → Pages
- Custom domain: storint.org
- Tick "Enforce HTTPS"
- Click Save

DNS takes 10 minutes to 48 hours to fully propagate.

---

## Things to add once it's up

### 1. Add your PDF toolkit
- Export your Canva toolkit as PDF
- Name it exactly: `toolkit.pdf`
- Upload it to the GitHub repo (same folder as the other files)
- In toolkit.html, find the line:
  `<!-- <iframe src="toolkit.pdf"...></iframe> -->`
  Remove the `<!--` and `-->` to uncomment it
- Delete the `<div class="pdf-placeholder">...</div>` block above it

### 2. Add your Google Form
- In Google Forms: Send → Embed icon (<>)
- Copy the src URL (looks like: https://docs.google.com/forms/d/e/XXXXX/viewform?embedded=true)
- In feedback.html, find: `src="YOUR_GOOGLE_FORM_EMBED_URL"`
- Replace that placeholder with your actual URL

### 3. Add Instagram and email
- Search all three HTML files for `ADD INSTAGRAM HANDLE HERE`
- Replace `@storint` with your actual handle (e.g. @storint_org)
- Replace the `href="#"` with your actual Instagram URL
- Search for `ADD EMAIL ADDRESS HERE`
- Replace `hello@storint.org` with your actual email address

### 4. Add team photos
- Add photos to a folder called `photos/` (create it in the repo)
- In index.html, find each team card and replace e.g.:
  `<div class="avatar">V</div>`
  with:
  `<div class="avatar"><img src="photos/vinnie.jpg" alt="Vinnie"></div>`

### 5. Update team names and roles
- In index.html, search for `ADD FIRST NAME HERE` and `ADD ROLE HERE`
- Update each team card with full names and specific roles

---

## Editing with Claude Code
If you have Claude Code installed:
- Open your terminal in the storint-website folder
- Describe the change you want in plain English, e.g.:
  "Change the hero headline to X"
  "Add a new team member called Sarah, role is Communications"
  "Update the email in the footer to team@storint.org"
- Claude Code will edit the file directly
- Then push to GitHub and the live site updates immediately

---

## Pushing updates to GitHub (after first upload)
Option A — drag and drop in the browser (easiest):
  GitHub repo → Add file → Upload files → drag new version → Commit

Option B — GitHub Desktop app (recommended for ongoing use):
  Download from https://desktop.github.com
  Clone your repo, edit files locally, click "Commit" and "Push"

Option C — Claude Code handles this automatically via terminal
