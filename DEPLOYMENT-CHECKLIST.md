# Vercel Deployment Checklist

## Pre-Deployment
- [ ] Verify `index.html` has correct Looker Studio report URL
- [ ] Test dashboard locally (`python -m http.server 3000`)
- [ ] Check all files are present:
  - [ ] index.html
  - [ ] vercel.json
  - [ ] package.json
  - [ ] .gitignore
  - [ ] README.md
  - [ ] TV-SETUP-GUIDE.md
  - [ ] DEPLOYMENT-CHECKLIST.md (this file)

## Git & Repository Setup
- [ ] Initialize Git repository: `git init`
- [ ] Add all files: `git add .`
- [ ] Create initial commit: `git commit -m "Initial commit: KTI Dashboard"`
- [ ] Create repository on GitHub/GitLab/Bitbucket
- [ ] Add remote: `git remote add origin <your-repo-url>`
- [ ] Verify remote: `git remote -v`
- [ ] Push to main: `git push -u origin main`

## Vercel Deployment
- [ ] Create Vercel account (if not existing): https://vercel.com
- [ ] Connect Git provider (GitHub/GitLab/Bitbucket)
- [ ] Import your repository
- [ ] Select "Other" as framework (or leave blank)
- [ ] Verify deployment settings
- [ ] Click "Deploy"
- [ ] Wait for deployment to complete (should be <1 minute)
- [ ] Note your custom domain (or request one)

## Post-Deployment Verification
- [ ] Visit deployment URL (e.g., `https://your-project.vercel.app`)
- [ ] Dashboard loads and displays correctly
- [ ] Iframe shows Looker Studio report
- [ ] All interactive elements work
- [ ] Test full-screen mode (F11)
- [ ] Check responsive design at different zoom levels

## TV Integration
- [ ] Configure displaying device (TV, browser, kiosk)
- [ ] Test on actual 42-inch display
- [ ] Verify resolution is appropriate (1920x1080 or higher)
- [ ] Check viewing distance (6-8 feet for 42-inch)
- [ ] Confirm auto-refresh is working (1-hour interval)
- [ ] Test screen visibility from different angles

## Monitoring & Maintenance Setup
- [ ] Enable notifications in Vercel (optional but recommended)
- [ ] Document the live URL
- [ ] Document Looker Studio report ID
- [ ] Set calendar reminder for monthly reviews
- [ ] Create backup plan if dashboard goes down

## Optional Enhancements (After Initial Deployment)
- [ ] Register custom domain on Vercel
- [ ] Set up automatic deployments for any future changes
- [ ] Add password protection if needed (via auth/middleware)
- [ ] Configure analytics tracking
- [ ] Set up error monitoring/logging

## Documentation
- [ ] Read README.md thoroughly
- [ ] Review TV-SETUP-GUIDE.md for your specific setup
- [ ] Document any customizations made
- [ ] Save admin credentials securely
- [ ] Create runbook for common troubleshooting

## Performance Testing
- [ ] Check page load time (should be <3 seconds)
- [ ] Monitor memory usage in browser
- [ ] Test on different browsers (Chrome, Firefox, Edge, Safari)
- [ ] Verify no console errors (F12)
- [ ] Test with slow network (DevTools throttling)

## Security Verification
- [ ] Verify HTTPS is enabled (check URL has 🔒)
- [ ] Confirm right-click menu is disabled
- [ ] Test that unwanted keyboard shortcuts don't work
- [ ] Verify Looker Studio permissions are appropriate
- [ ] Check no sensitive data is exposed in URL

## Troubleshooting Steps
If deployment fails:
1. [ ] Check Vercel deployment logs for errors
2. [ ] Verify all files are in repository
3. [ ] Ensure vercel.json is valid JSON
4. [ ] Check Git history: `git log --oneline`
5. [ ] Try redeploying from Vercel dashboard

If dashboard doesn't display:
1. [ ] Verify Looker Studio report URL is correct
2. [ ] Ensure report is "Viewer accessible" or public
3. [ ] Check browser console (F12 → Console tab)
4. [ ] Clear browser cache (Ctrl+Shift+Delete)
5. [ ] Try incognito/private window
6. [ ] Verify internet connection

## Going Live Checklist
- [ ] All above items completed
- [ ] 24-hour uptime verification
- [ ] Dashboard performs as expected
- [ ] TV display shows correctly
- [ ] Data refreshes as intended
- [ ] Team is aware of live deployment
- [ ] Backup/emergency procedures documented
- [ ] Support contact information available

## Long-Term Maintenance
- [ ] Monthly: Review dashboard performance
- [ ] As needed: Update Looker Studio report
- [ ] As needed: Update dashboard content
- [ ] Quarterly: Review security and access
- [ ] Annual: Evaluate dashboard effectiveness

---

**Deployment Date**: _______________
**Live URL**: _______________
**Deployed By**: _______________
**Notes**: _______________________________________________

---

## Quick Reference Commands

```bash
# Local testing
python -m http.server 3000

# Deploy with Vercel CLI
npm install -g vercel
vercel

# View deployment logs
vercel logs

# Rollback to previous deployment
vercel rollback

# List all deployments
vercel list
```

## Support Resources

- **Vercel Docs**: https://vercel.com/docs
- **Looker Studio Support**: https://support.google.com/looker-studio
- **GitHub Issues**: Create issue in your repository
- **Community Help**: https://vercel.com/support
