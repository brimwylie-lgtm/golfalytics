# Troubleshooting: CSS Not Loading

## Problem
You see the HTML content but no styling (colors, layout, design).

## Most Likely Cause
You're opening the HTML file directly in your browser (file:// URL) instead of through a web server.

## Solution: Run a Local Web Server

You have 3 easy options:

### Option 1: Python (Easiest if you have Python)

1. Open Terminal/Command Prompt
2. Navigate to the golfalytics-site folder:
   ```bash
   cd path/to/golfalytics-site
   ```
3. Run:
   ```bash
   # Python 3
   python3 -m http.server 8000
   
   # OR Python 2
   python -m SimpleHTTPServer 8000
   ```
4. Open your browser to: `http://localhost:8000`

### Option 2: Node.js (If you have npm)

1. Open Terminal/Command Prompt
2. Navigate to the golfalytics-site folder
3. Run:
   ```bash
   npx serve
   ```
4. Open the URL it provides (usually `http://localhost:3000`)

### Option 3: VS Code Live Server

1. Open the folder in VS Code
2. Install "Live Server" extension
3. Right-click on index.html
4. Click "Open with Live Server"

### Option 4: Just Deploy to Vercel Now

If the above seems complicated, just deploy to Vercel right now:

1. Create GitHub repo
2. Push code to GitHub
3. Connect to Vercel
4. View the live site

The CSS will work perfectly on Vercel!

## Why This Happens

When you open an HTML file directly:
- URL looks like: `file:///Users/you/Desktop/golfalytics-site/index.html`
- Some browsers restrict loading external CSS/JS files for security
- The `<link rel="stylesheet" href="styles.css">` may be blocked

When you use a web server:
- URL looks like: `http://localhost:8000`
- Browser treats it like a real website
- All files load normally

## Quick Test

1. Open `test.html` in your browser (same way you opened index.html)
2. If you see a RED background, CSS isn't loading
3. Run one of the web servers above
4. Open `test.html` through the server
5. You should see content with the CSS applied

## Alternative: View Deployed Version

The site will look perfect once deployed to Vercel. If you just want to see it working now:

1. Follow DEPLOYMENT.md
2. Deploy to Vercel (takes 2 minutes)
3. View the live site with full styling

## Still Not Working?

Check these:

1. **File Structure**: Make sure styles.css is in the SAME folder as index.html
   ```
   golfalytics-site/
   ├── index.html
   ├── styles.css    ← Must be here
   ├── script.js
   └── ...
   ```

2. **File Names**: 
   - CSS file must be named exactly `styles.css` (lowercase, no spaces)
   - HTML file links to `styles.css`

3. **Browser Cache**: 
   - Try hard refresh (Ctrl+Shift+R or Cmd+Shift+R)
   - Or open in incognito/private window

4. **Browser Console**:
   - Press F12 to open developer tools
   - Look for errors in the Console tab
   - Check the Network tab to see if styles.css loaded

## Expected Result

When working correctly, you should see:
- ✅ Green navigation with white text
- ✅ Large green hero section with "Turn Golf Course Audiences..."
- ✅ Stats grid with large green numbers
- ✅ Styled cards and sections
- ✅ Green buttons and links
- ✅ Professional layout and spacing

## Quick Deploy to See It Working

Fastest way to see the site working perfectly:

```bash
# In the golfalytics-site folder
git init
git add .
git commit -m "Initial commit"

# Create repo on GitHub, then:
git remote add origin YOUR_GITHUB_URL
git push -u origin main

# Then deploy on Vercel - takes 60 seconds!
```

The deployed version will look perfect with all styling applied!
