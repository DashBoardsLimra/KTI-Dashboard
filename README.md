# KTI Sales Dashboard

A responsive Looker Studio dashboard optimized for 42-inch LED TV displays, deployed on Vercel.

## Features

- ✅ **Responsive Design**: Automatically scales to fit 42-inch LED TV (1920x1080 and higher)
- ✅ **Full-Screen Display**: Optimized for kiosk/TV mode
- ✅ **Auto-Refresh**: Dashboard refreshes every hour
- ✅ **Performance Optimized**: Fast loading with proper caching headers
- ✅ **Security**: CORS and security headers configured
- ✅ **No Build Required**: Static HTML - zero dependencies

## Deployment Instructions

### Step 1: Prepare for Git

```bash
# Initialize git repository (if not done)
git init
git add .
git commit -m "Initial commit: KTI Dashboard"
```

### Step 2: Push to GitHub/GitLab/Bitbucket

```bash
# Create a repository on GitHub (or your preferred platform)
# Add remote and push
git remote add origin <your-repo-url>
git branch -M main
git push -u origin main
```

### Step 3: Deploy to Vercel

#### Option A: Vercel Dashboard (Recommended)

1. Go to [https://vercel.com](https://vercel.com)
2. Sign in with GitHub/GitLab account
3. Click **"New Project"**
4. Import your repository
5. Vercel will auto-detect it's a static site
6. Click **"Deploy"**
7. Your dashboard will be live at: `https://your-project.vercel.app`

#### Option B: Vercel CLI

```bash
# Install Vercel CLI
npm install -g vercel

# Deploy from project directory
vercel
```

### Step 4: Configure for TV Display

1. **Access the dashboard**: Visit your Vercel URL on the 42-inch TV
2. **Full-Screen Mode**: The dashboard will attempt to enter full-screen mode automatically
3. **Keyboard Shortcuts**:
   - Press `F11` to toggle full-screen manually
   - Right-click is disabled to prevent accidental navigation
4. **Security**: Power off the TV to prevent unwanted interactions

## Local Testing

### Run Locally

```bash
# Using Python (recommended)
python -m http.server 3000

# Or using Node.js http-server
npx http-server -p 3000

# Then visit: http://localhost:3000
```

### Test Responsiveness

- Open DevTools (F12) and use Device Emulation
- Test at 1920x1080 resolution (42" TV standard)
- Test at 4K (3840x2160) for future-proofing

## Customization

### Adjust Refresh Interval

Edit `index.html` and change the `REFRESH_INTERVAL` value (in milliseconds):

```javascript
const REFRESH_INTERVAL = 3600000; // Default: 1 hour = 3,600,000 ms
// For 30 minutes: 1800000
// For 24 hours: 86400000
```

### Change Title

Edit the `<title>` tag in the HTML head section.

### Update Dashboard URL

If your Looker Studio report changes, update the `src` attribute in the `<iframe>` tag.

## 42-Inch LED TV Optimization Details

### Display Specifications
- **Resolution**: 1920x1080 (Full HD) to 3840x2160 (4K)
- **Aspect Ratio**: 16:9
- **Viewing Distance**: 6-8 feet recommended
- **Font Size**: Scaled for TV readability

### CSS Features
- **100% Viewport Coverage**: Uses `100vw` and `100vh` for full coverage
- **No Scrolling**: Disabled to prevent accidental scrolling
- **Dark Background**: Reduces eye strain during extended viewing
- **Responsive Typography**: Text automatically scales with display

## Monitoring

### Check Deployment Status
- Visit your Vercel dashboard
- Check build logs and deployment history
- Monitor analytics and performance metrics

### Get Notification for Failures
1. Configure notifications in Vercel project settings
2. Integrate with Slack, Teams, or email

## Troubleshooting

### Dashboard Not Loading
- Check internet connection
- Verify Looker Studio report is public/embeddable
- Check browser console for errors (F12)

### Not Full-Screen on TV
- Some browsers require user interaction for full-screen
- Try manual full-screen toggle with F11
- Verify browser permissions allow full-screen

### Poor Performance
- Clear browser cache
- Check network speed
- Reload the page (Ctrl+Shift+R for hard refresh)

### Looker Studio Report Issues
- Verify the report URL is correct in iframe
- Ensure report is shared with "Viewer" access or public
- Check Google account permissions

## Security Notes

- The dashboard disables right-click menu
- Google Analytics is disabled for privacy
- Keyboard shortcuts are restricted for TV mode
- CORS headers prevent embedding in untrusted sources

## Support

For issues:
1. Check Vercel deployment logs
2. Verify Looker Studio report is accessible
3. Clear browser cache and reload
4. Try accessing from a different device

## License

MIT - Feel free to modify and reuse

## Environment

- **Deployment**: Vercel (serverless)
- **Content**: Looker Studio
- **Framework**: Vanilla HTML/CSS/JavaScript
- **Compatibility**: Modern browsers (Chrome, Safari, Edge, Firefox)
