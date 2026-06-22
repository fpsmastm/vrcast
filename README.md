# QuestCast 🥽

Cast your **Meta Quest 2** to your Chromebook — a simple static site hosted on Cloudflare Pages.

## What this does

Gives you a clean guide page (at your own domain/URL) that walks you through casting your Quest 2 to a browser tab on your Chromebook. The actual video stream goes through Meta's official casting infrastructure — this page just makes it easy to remember the steps and jump straight to the receiver.

---

## Deploy in 3 steps

### 1 — Push to GitHub

```bash
git init
git add .
git commit -m "init questcast"
git branch -M main
git remote add origin https://github.com/YOUR_USERNAME/vr-cast.git
git push -u origin main
```

### 2 — Connect to Cloudflare Pages

1. Go to [dash.cloudflare.com](https://dash.cloudflare.com) → **Workers & Pages** → **Create application** → **Pages** → **Connect to Git**
2. Pick your `vr-cast` repo
3. Set these build settings:

| Setting | Value |
|---|---|
| Framework preset | None |
| Build command | *(leave blank)* |
| Build output directory | `public` |

4. Click **Save and Deploy** — Cloudflare gives you a free `*.pages.dev` URL instantly.

### 3 — (Optional) Custom domain

In Cloudflare Pages → your project → **Custom domains** → add your domain.

---

## How to cast from your Quest 2

1. Put on your Quest 2 and press the **Meta button** (right controller)
2. Go to **Sharing → Cast → This Computer**
3. Press **Start**
4. On your Chromebook, open your site URL and click **"Open Cast Receiver"**
5. Sign in with the **same Meta account** — stream appears!

### Tips
- Use **5 GHz Wi-Fi** — both devices on the same network
- Use **Google Chrome** on your Chromebook (not another browser)
- The shortcut URL `yoursite.pages.dev/go` redirects straight to the receiver

---

## File structure

```
vr-cast/
├── public/
│   ├── index.html     # Main page
│   ├── style.css      # Styles
│   ├── _redirects     # Cloudflare redirect rules
│   └── _headers       # Security & cache headers
├── wrangler.toml      # Cloudflare config
└── README.md
```
