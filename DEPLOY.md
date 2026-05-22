# Deploy wedding invitation

Host at **https://salihwedding.codeteak.com** using GitHub Pages (recommended) or upload directly to CodeTeak hosting.

Your site is static: `index.html`, `images/`, `audio/`. No build step required.

---

## Option A — GitHub Pages + custom domain (recommended)

Use GitHub for hosting and point `salihwedding.codeteak.com` to it.

### Step 1 — Create a GitHub repository

1. Go to [github.com/new](https://github.com/new).
2. Repository name example: `salih-wedding` (any name is fine).
3. Set **Public** (required for free GitHub Pages on personal accounts).
4. Do **not** add README, .gitignore, or license (you already have files locally).
5. Click **Create repository**.

### Step 2 — Push your project (run in Terminal)

**Important:** Run these commands **inside** the `SaliMarriage` folder only, not your home folder.

```bash
cd /Users/muhammedrizwan/SaliMarriage

git init
git add index.html images/ audio/ README.md DEPLOY.md .gitignore .nojekyll
git commit -m "Add Salih & Saniya wedding invitation"

git branch -M main
git remote add origin https://github.com/YOUR_GITHUB_USERNAME/salih-wedding.git
git push -u origin main
```

Replace `YOUR_GITHUB_USERNAME` and `salih-wedding` with your real GitHub username and repo name.

### Step 3 — Enable GitHub Pages

1. Open the repo on GitHub → **Settings** → **Pages**.
2. **Build and deployment**
   - Source: **Deploy from a branch**
   - Branch: **main** → folder **/ (root)** → **Save**
3. Wait 1–3 minutes. Your site will be live at:

   `https://YOUR_GITHUB_USERNAME.github.io/salih-wedding/`

   (If the repo is named `YOUR_GITHUB_USERNAME.github.io`, the URL is just `https://YOUR_GITHUB_USERNAME.github.io/`.)

### Step 4 — Connect `salihwedding.codeteak.com`

You need access to **DNS for codeteak.com** (Cloudflare, Namecheap, GoDaddy, cPanel, etc.).

**On GitHub:**

1. Repo → **Settings** → **Pages** → **Custom domain**.
2. Enter: `salihwedding.codeteak.com` → **Save**.
3. GitHub will ask you to verify DNS. Enable **Enforce HTTPS** when it becomes available.

**Create this file in your project** (GitHub adds it automatically when you set the domain; you can also add it yourself):

```
# File: CNAME  (no extension, in project root)
salihwedding.codeteak.com
```

Then commit and push:

```bash
cd /Users/muhammedrizwan/SaliMarriage
echo "salihwedding.codeteak.com" > CNAME
git add CNAME
git commit -m "Add custom domain"
git push
```

**In DNS for codeteak.com**, add:

| Type  | Name / Host      | Value / Target                          |
|-------|------------------|-----------------------------------------|
| CNAME | `salihwedding`   | `YOUR_GITHUB_USERNAME.github.io`        |

Examples:

- Host: `salihwedding` → Points to: `johndoe.github.io` (replace with your username)
- Do **not** include `https://` in the DNS value.

DNS can take **5 minutes to 48 hours** to propagate. Then open:

**https://salihwedding.codeteak.com**

### Step 5 — Update later

After editing `index.html`, images, or audio:

```bash
cd /Users/muhammedrizwan/SaliMarriage
git add -A
git commit -m "Update invitation"
git push
```

GitHub Pages redeploys automatically in about 1–2 minutes.

---

## Option B — Host only on CodeTeak (no GitHub)

Use this if you have a server or control panel under **codeteak.com** (cPanel, VPS, Fleek, etc.).

### Step 1 — Upload files

Upload **everything** in `SaliMarriage` to the web root for the subdomain, keeping folders:

```
public_html/   (or site root for salihwedding)
├── index.html
├── images/
│   └── saalimarriage.jpg
├── audio/
│   └── saliAudio.mp3
├── .nojekyll    (optional; harmless)
└── ...
```

Ways to upload:

- **cPanel** → File Manager → `public_html` or subdomain folder
- **SFTP** (FileZilla, Cyberduck): host, username, password from your host
- **SSH**: `scp -r /Users/muhammedrizwan/SaliMarriage/* user@server:/path/to/salihwedding/`

`index.html` must be in the **root** of that subdomain folder.

### Step 2 — DNS for subdomain

In DNS for **codeteak.com**:

| Type | Name           | Value                    |
|------|----------------|--------------------------|
| A    | `salihwedding` | Your server IP address   |
| or CNAME | `salihwedding` | Your host’s target hostname |

Ask whoever manages **codeteak.com** (CodeTeak team / hosting provider) for the correct IP or CNAME.

### Step 3 — HTTPS

Enable SSL in your hosting panel (Let’s Encrypt / Auto SSL) for `salihwedding.codeteak.com`.

### Step 4 — Test

Open **https://salihwedding.codeteak.com** — tap **Open Invitation** to test music and photo.

---

## Option C — GitHub + CodeTeak (both)

Common setup:

- **GitHub** = source code + automatic deploy (Option A).
- **salihwedding.codeteak.com** = CNAME to GitHub Pages (Step 4 in Option A).

You do **not** need Option B if GitHub Pages handles the subdomain.

---

## Checklist before going live

- [ ] `images/saalimarriage.jpg` loads
- [ ] `audio/saliAudio.mp3` plays after “Open Invitation”
- [ ] Nikkah & reception show **14 June 2026**
- [ ] Map links open correctly
- [ ] Test on mobile (Safari + Chrome)
- [ ] Share link uses **https://** (not http)

---

## Troubleshooting

| Problem | Fix |
|--------|-----|
| 404 on GitHub Pages | Repo is Public; Pages enabled on `main` / root; wait a few minutes |
| Photo or music missing | Paths must stay `images/...` and `audio/...`; check file names match `CONFIG` in `index.html` |
| Custom domain not working | DNS CNAME must point to `username.github.io`; wait for DNS propagation |
| Music does not autoplay | Normal on iPhone — user must tap **Open Invitation** |
| Repo too large | Keep audio under ~10 MB (yours is fine) |

---

## Who to contact for `codeteak.com` DNS

If you do not manage **codeteak.com** DNS yourself, send your hosting person:

> Please add a CNAME record: **salihwedding** → **YOUR_GITHUB_USERNAME.github.io**  
> (for GitHub Pages)  
> or point **salihwedding.codeteak.com** to our web server for static files.

Replace `YOUR_GITHUB_USERNAME` with your actual GitHub username.
