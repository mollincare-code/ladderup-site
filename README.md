# Ladderup Corporate Advisory — CMS-Powered Website

## What's Inside

```
ladderup-cms/
├── index.html                ← Main website (auto-renders from JSON)
├── netlify.toml              ← Netlify deploy config
├── admin/
│   ├── index.html            ← CMS admin panel
│   └── config.yml            ← CMS field definitions
├── content/                  ← All editable content (JSON)
│   ├── settings.json         ← Logo, nav links, site title
│   ├── hero.json             ← Hero headline, stats, quote
│   ├── value-proposition.json
│   ├── services.json
│   ├── advisory.json
│   ├── why-ladderup.json
│   ├── cta.json
│   ├── footer.json
│   └── testimonials/
│       └── manufacturing-client.json
└── images/
    ├── logo.png
    └── uploads/              ← CMS-uploaded images
```

## How It Works

1. Client visits `yoursite.com/admin`
2. Logs in via Netlify Identity
3. Edits content through visual editor (no code needed)
4. Clicks Publish -> JSON commits to GitHub
5. Netlify auto-rebuilds -> site live in ~30 seconds

## Deployment (One-Time)

### 1. Push to GitHub
```bash
cd ladderup-cms
git init && git add . && git commit -m "Initial site"
git remote add origin https://github.com/YOU/ladderup.git
git push -u origin main
```

### 2. Deploy on Netlify
- netlify.com -> Add new site -> Import from GitHub
- Publish directory: `.`  (build command: leave empty)

### 3. Enable CMS Auth
- Site settings -> Identity -> Enable Identity
- Registration: Invite only
- Services -> Git Gateway -> Enable
- Identity tab -> Invite users -> add client email

### 4. Update config.yml
- Change `site_url` to your actual Netlify URL

## What's Editable

| Section | Fields |
|---------|--------|
| Settings | Logo, nav links, CTA button |
| Hero | Headline, description, stats, quote, buttons |
| Value Proposition | Tag, text, lifecycle steps |
| Services | Cards (title, description) |
| Advisory | Cards, CTA button |
| Why Ladderup | Features, tagline |
| Testimonials | Add/edit/delete (quote, author) |
| CTA | Headline, button |
| Footer | All links, copyright, SEBI reg |
| Images | Upload via media library |

## Cost: $0/month (Netlify free tier)
