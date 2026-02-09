# TV Display Configuration & Setup Guide

## Physical TV Setup (42-inch LED)

### Resolution & Display Settings
- **Recommended Resolution**: 1920x1080 (Full HD) minimum, 3840x2160 (4K) optimal
- **Aspect Ratio**: 16:9 (standard widescreen)
- **Refresh Rate**: 60Hz standard
- **Color Mode**: Standard or Vibrant (adjust for room lighting)

### Optimal Viewing

```
Display Type: 42-inch LED TV
Resolution: 1920x1080 or 4K (3840x2160)
Viewing Distance: 6-8 feet
Optimal Distance: 2.5 × screen width (approximately 7-8 feet)
Brightness: 20-40% (to reduce eye strain for 24/7 display)
Contrast: 45-55% (default)
```

### Anti-Burn-in Settings (for 24/7 Display)

If displaying continuously:
1. Enable **Pixel Shifting** in TV settings
2. Use **Contrast Reduction** during off-peak hours
3. Consider **Screen Saver** timeout of 30 minutes
4. Reduce brightness to 20-30% for night mode

### Network Configuration

```
Connection Type: Ethernet (recommended) or Wi-Fi (2.4GHz/5GHz)
Bandwidth Required: 5-10 Mbps
Latency: < 100ms recommended
Uptime: Critical - ensure stable internet
Router: Place near TV or use Wi-Fi extender
```

## Browser Setup (Chrome/Firefox/Edge)

### Kiosk Mode (Recommended for TV)

#### Google Chrome
```batch
# Windows - Run in Kiosk Mode
"C:\Program Files\Google\Chrome\Application\chrome.exe" 
  --kiosk 
  --disable-translate 
  --no-first-run 
  https://your-vercel-url.vercel.app
```

#### Firefox
```batch
"C:\Program Files\Mozilla Firefox\firefox.exe" 
  --fullscreen 
  https://your-vercel-url.vercel.app
```

### Browser Extensions to Disable
- AdBlockers
- VPNs
- Password managers
- Privacy extensions

### Browser Settings

| Setting | Value | Reason |
|---------|-------|--------|
| Auto-play | Enabled | Smooth dashboard loading |
| JavaScript | Enabled | Required for Looker Studio |
| Cookies | Enabled | Authentication persistence |
| Cache | 100MB+ | Faster repeated loads |
| Hardware Acceleration | Enabled | Better performance on large displays |

## Automatic Startup

### Windows Task Scheduler

```batch
# Create scheduled task to launch browser on startup
# Administrator PowerShell:

$Action = New-ScheduledTaskAction -Execute 'C:\Program Files\Google\Chrome\Application\chrome.exe' `
  -Argument '--kiosk --no-first-run https://your-vercel-url.vercel.app'
$Trigger = New-ScheduledTaskTrigger -AtStartup
$Principal = New-ScheduledTaskPrincipal -UserId "$env:COMPUTERNAME\$env:USERNAME" -RunLevel Highest
Register-ScheduledTask -TaskName "KTI-Dashboard" -Action $Action -Trigger $Trigger -Principal $Principal
```

### macOS (launchd)

Create `~/Library/LaunchAgents/com.kti.dashboard.plist`:

```xml
<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd">
<plist version="1.0">
<dict>
    <key>Label</key>
    <string>com.kti.dashboard</string>
    <key>ProgramArguments</key>
    <array>
        <string>/Applications/Google Chrome.app/Contents/MacOS/Google Chrome</string>
        <string>--kiosk</string>
        <string>https://your-vercel-url.vercel.app</string>
    </array>
    <key>RunAtLoad</key>
    <true/>
    <key>KeepAlive</key>
    <true/>
</dict>
</plist>
```

### Linux (systemd)

Create `/etc/systemd/system/kti-dashboard.service`:

```ini
[Unit]
Description=KTI Dashboard
After=network.target

[Service]
Type=simple
User=pi
ExecStart=/usr/bin/chromium-browser --kiosk --no-first-run https://your-vercel-url.vercel.app
Restart=on-failure
RestartSec=10

[Install]
WantedBy=multi-user.target
```

## Performance Optimization

### Content Delivery
- **CDN**: Vercel's global CDN ensures fast loading worldwide
- **Caching**: 5-minute cache for dynamic content, 1-hour cache for static
- **Compression**: Gzip compression enabled by default

### Bandwidth Saving
- Dashboard data: ~2-5 MB per load
- Auto-refresh: Every 60 minutes (minimal data usage)
- Typical monthly usage: 2-4 GB for continuous display

## Monitoring & Maintenance

### Daily Checks
- [ ] Dashboard loads without errors
- [ ] All charts and metrics display correctly
- [ ] No console errors (F12 Developer Tools)
- [ ] Screen brightness/contrast appropriate

### Weekly Maintenance
- [ ] Verify data is current (last refresh time visible)
- [ ] Check internet connectivity
- [ ] Clear browser cache if needed
- [ ] Monitor for any glitches or anomalies

### Monthly Tasks
- [ ] Review dashboard performance metrics
- [ ] Update Looker Studio report if needed
- [ ] Check for browser updates
- [ ] Verify TV display settings haven't changed

## Troubleshooting TV Display Issues

### Black Screen
- Check HDMI cable connection
- Verify input source is correct
- Restart TV and computer
- Check if monitor sleep settings are enabled

### Dashboard Not Displaying
1. Open DevTools (F12)
2. Check Console tab for errors
3. Verify internet connection
4. Clear browser cache (Ctrl+Shift+Delete)
5. Reload page (F5)

### Performance Issues
- Check browser tab count (close unnecessary tabs)
- Monitor CPU/Memory (Task Manager)
- Reduce refresh frequency if needed
- Disable browser extensions

### Audio Issues (if applicable)
- Verify volume settings on TV
- Check audio output in browser settings
- Test with different audio output device

## Security Considerations

### Physical Security
- Place TV in secure location
- Consider lockable viewing area
- Limit physical access to power/inputs

### Network Security
- Use strong Wi-Fi password (WPA3 preferred)
- Enable TV firewall if available
- Consider separate network for dashboard

### Browser Security
- Keep browser updated
- Disable unnecessary plugins
- Use only HTTPS connections

## Emergency Recovery

### If Dashboard Freezes
1. Press Alt+Tab to switch windows
2. Close browser and reopen
3. Hard restart if needed (hold power button)

### Data Loss Prevention
- Vercel automatically maintains backups
- Looker Studio data is cloud-stored
- No local data at risk

### Backup Access
- Keep Looker Studio URL documented
- Save mobile/backup access method
- Document all admin credentials

## Contact & Support

- **Vercel Status**: https://vercel.com/status
- **Looker Studio Help**: https://support.google.com/looker-studio
- **Browser Issues**: Check respective browser support pages
