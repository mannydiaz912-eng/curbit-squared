# Curb-It² Website

**curbitsquared.com** — Lawn Mower Repair in East Markham, ON

---

## 🚀 Quick Start

### Prerequisites
- Node.js 18+
- npm or pnpm
- Cloudflare account (for deployment)
- Namecheap domain: `curbitsquared.com`

### Local Development

```bash
# 1. Install dependencies
npm install

# 2. Start dev server (localhost:4321)
npm run dev
```

---

## ☁️ Deploy to Cloudflare Pages

### First-Time Setup

**1. Install Wrangler (Cloudflare CLI)**
```bash
npm install -g wrangler
wrangler login
```

**2. Build the site**
```bash
npm run build
```

**3. Deploy to Cloudflare Pages**
```bash
# Create project first time
wrangler pages project create curbit-squared

# Deploy
wrangler pages deploy dist --project-name curbit-squared
```

### Connect Your Domain (Namecheap → Cloudflare)

1. Go to [dash.cloudflare.com](https://dash.cloudflare.com) → Add a Site → `curbitsquared.com`
2. Cloudflare will give you **2 nameservers** (e.g. `aria.ns.cloudflare.com`)
3. Log into **Namecheap** → Domain List → curbitsquared.com → Nameservers
4. Change to "Custom DNS" → paste Cloudflare's nameservers → Save
5. Wait 24–48h for propagation

### Set Custom Domain in Cloudflare Pages
1. Cloudflare Dashboard → Pages → curbit-squared → Custom Domains
2. Add `curbitsquared.com` and `www.curbitsquared.com`
3. Cloudflare auto-provisions SSL ✅

---

## 📁 Project Structure

```
curbit-squared/
├── public/
│   ├── images/
│   │   ├── logo.jpg         ← Curb-It² logo
│   │   ├── hero-mowers.jpg  ← Hero background
│   │   ├── repair-work.jpg  ← About section
│   │   └── inventory.jpg    ← Gallery
│   └── favicon.svg
├── src/
│   ├── layouts/
│   │   └── Layout.astro     ← Nav, footer, global styles, fonts
│   ├── components/
│   │   ├── Hero.astro
│   │   ├── Services.astro
│   │   ├── About.astro
│   │   ├── Gallery.astro
│   │   └── Contact.astro
│   └── pages/
│       └── index.astro      ← Main page
├── astro.config.mjs
├── wrangler.toml
└── package.json
```

---

## 📬 Contact Form

The form uses [FormSubmit.co](https://formsubmit.co/) — a free, no-backend form service.

- Submissions go to: `curbitsquared@gmail.com`
- First submission will trigger an email confirmation from FormSubmit — click the link to activate.
- No server code needed.

---

## 🎨 Brand Colors

| Name | Hex | Usage |
|------|-----|-------|
| Deep Green | `#0B6B3A` | Primary brand, nav, headings |
| Bright Orange | `#F47C20` | CTA buttons, accents |
| Charcoal Black | `#1F1F1F` | Body text |
| Warm Off-White | `#F7F4EC` | Page background |
| Grass Green | `#7FBF3F` | Hover states |

---

## 🔄 Ongoing Deployments

After any changes:
```bash
npm run build
wrangler pages deploy dist --project-name curbit-squared
```

Or connect your **GitHub repo** to Cloudflare Pages for automatic deploys on push.
