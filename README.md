# KTI Sales Dashboard

A responsive Looker Studio dashboard optimized for 42-inch LED TV displays, deployed on Vercel.

## ✅ Features

- 🎯 **Responsive Design**: Automatically scales to 1920x1080 and 4K
- 📺 **Full-Screen Display**: Optimized for TV kiosk mode
- 🔄 **Auto-Refresh**: Refreshes every hour
- ⚡ **Zero Build**: Static HTML - no dependencies
- 🚀 **Fast Deploy**: Live in seconds

## 📁 Project Structure

```
├── index.html              # Dashboard + Looker embed + TV optimization
├── vercel.json            # Minimal Vercel config
├── .gitignore             # Git ignore rules
├── README.md              # This file
├── TV-SETUP-GUIDE.md      # TV physical setup & browser config
└── DEPLOYMENT-CHECKLIST.md # Pre/post deployment checks
```

## 🚀 Quick Start (3 Steps)

### Step 1: Prepare Git
```bash
cd KTI-Dashboard
git init
git add .
git commit -m "Initial: KTI Dashboard"
```

### Step 2: Push to GitHub
```bash
git remote add origin https://github.com/YOUR-USERNAME/KTI-Dashboard.git
git branch -M main
git push -u origin main
```

### Step 3: Deploy to Vercel

**Option A: Vercel Dashboard**
1. Go to https://vercel.com → Sign in with GitHub
2. Click "New Project" → Select `KTI-Dashboard`
3. Click "Deploy"
4. ✅ Done! Live at `https://kti-dashboard.vercel.app`

**Option B: Vercel CLI**
```bash
npm install -g vercel
vercel
```

## 🧪 Local Testing

```bash
# Start local server
python -m http.server 3000

# Visit: http://localhost:3000
```

## 📝 Customization

### Change Auto-Refresh Interval

Edit `index.html`, find `REFRESH_INTERVAL`:

```javascript
const REFRESH_INTERVAL = 3600000; // 1 hour = default
// 300000 = 5 min | 1800000 = 30 min | 86400000 = 24 hrs
```

### Update Looker Studio Report

Edit the iframe `src` URL in `index.html`:

```html
<iframe src="https://lookerstudio.google.com/embed/reporting/YOUR-REPORT-ID/..." ...></iframe>
```

### Change Dashboard Title

Edit `index.html` `<title>` tag:

```html
<title>Your Dashboard Title</title>
```

## 📺 42-Inch TV Optimization

`index.html` includes:
- ✅ Responsive CSS (1920x1080 + 4K)
- ✅ 100% viewport coverage (no scrolling)
- ✅ Dark theme (reduces eye strain)
- ✅ Auto-fullscreen support
- ✅ Keyboard shortcuts disabled
- ✅ Right-click menu disabled

See **TV-SETUP-GUIDE.md** for:
- Physical TV settings optimization
- Browser kiosk mode setup
- Windows/Mac/Linux auto-startup
- 24/7 display configurations

## ❓ Troubleshooting

| Problem | Solution |
|---------|----------|
| Deployment fails | Verify vercel.json syntax, check index.html exists |
| Blank dashboard | Ensure Looker report is public/shareable |
| Not full-screen | Press F11 or setup browser per TV-SETUP-GUIDE.md |
| Slow loading | Clear browser cache (Ctrl+Shift+Delete) |
| Looker errors | Check Looker report URL & sharing settings |

## 🔗 Resources

- **Vercel Docs**: https://vercel.com/docs
- **Looker Studio Help**: https://support.google.com/looker-studio
- **Status**: https://vercel.com/status

## 📄 Files Reference

| File | Purpose |
|------|---------|
| `index.html` | Main dashboard (Looker embed + responsive CSS) |
| `vercel.json` | Minimal deployment config |
| `.gitignore` | Git ignore patterns |
| `TV-SETUP-GUIDE.md` | TV setup, browser config, auto-startup |
| `DEPLOYMENT-CHECKLIST.md` | Pre/post deployment verification |

## 📞 Support

- Read **TV-SETUP-GUIDE.md** for TV configuration questions
- Check **DEPLOYMENT-CHECKLIST.md** for verification steps
- Review browser console (F12) for error messages

## 📜 License

MIT - Modify and reuse freely

---

**Ready to deploy?** Follow the 3-step Quick Start above! 🎉
