# Concept Studio MARA — Deploy Guide

This folder is ready to publish as-is. It contains:
- `index.html` — the site
- `assets/` — logo, hero photo, about photo
- `CNAME` — tells GitHub Pages to serve this at conceptstudiomara.com

## First-time setup

### 1. Create the GitHub repo
1. Go to https://github.com/new
2. Repository name: `conceptstudio-mara-website`
3. Choose Public or Private (Private works fine with GitHub Pages on a paid plan; if you're on the free plan, use Public)
4. Click **Create repository** (don't initialize with a README — leave it empty)

### 2. Upload these files
1. On the new repo's page, click **"uploading an existing file"**
2. Drag in `index.html`, `CNAME`, and the whole `assets` folder from this download
3. Commit directly to the `main` branch

### 3. Turn on GitHub Pages
1. In the repo, go to **Settings → Pages**
2. Under "Build and deployment" → Source, choose **Deploy from a branch**
3. Branch: `main`, folder: `/ (root)` → Save
4. Under "Custom domain", enter `conceptstudiomara.com` and Save
   (this matches the CNAME file already in the upload)
5. GitHub will show a DNS check — that's expected until step 4 below is done

### 4. Point your domain at GitHub Pages
Go to your domain registrar's DNS settings (wherever you bought conceptstudiomara.com) and add:

**A records** (for the root domain conceptstudiomara.com) — add all four:
```
185.199.108.153
185.199.109.153
185.199.110.153
185.199.111.153
```

**CNAME record** (for www.conceptstudiomara.com):
```
www → <your-github-username>.github.io
```

DNS changes can take a few minutes up to 24 hours to propagate. Once live, GitHub auto-provisions HTTPS (check "Enforce HTTPS" in Pages settings once the domain verifies).

## Updating the site later

Whenever you want to make changes:
1. Keep chatting with Claude in this project to edit the design
2. When ready to publish, ask Claude to "prepare a deploy export"
3. Download the new `deploy` folder
4. In your GitHub repo, upload the new `index.html` (and any changed assets) — GitHub lets you drag files onto the existing repo page and it will overwrite files with the same name
5. Commit — GitHub Pages rebuilds automatically within about a minute

No terminal or git commands needed for any of this.
