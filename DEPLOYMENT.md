# Golfalytics Deployment Guide

## Quick Start: GitHub to Vercel Deployment

### Step 1: Create GitHub Repository

1. Go to https://github.com and create a new repository
   - Name it: `golfalytics` (or whatever you prefer)
   - Make it Public or Private
   - Don't initialize with README (you already have one)

### Step 2: Push Code to GitHub

Open terminal in the `golfalytics-site` folder and run:

```bash
# Initialize git
git init

# Add all files
git add .

# Commit
git commit -m "Initial Golfalytics site"

# Add your GitHub repository as remote
git remote add origin https://github.com/YOUR-USERNAME/golfalytics.git

# Push to GitHub
git branch -M main
git push -u origin main
```

Replace `YOUR-USERNAME` with your actual GitHub username.

### Step 3: Deploy to Vercel

1. Go to https://vercel.com and sign in with GitHub
2. Click "Add New..." → "Project"
3. Find your `golfalytics` repository and click "Import"
4. Vercel will auto-detect it as a static site
5. Click "Deploy" (no configuration needed!)
6. Wait 30-60 seconds for deployment

Your site will be live at: `https://golfalytics.vercel.app`

### Step 4: Add Custom Domain (Optional)

If you own `golfalytics.ca`:

1. In Vercel project → Settings → Domains
2. Add `golfalytics.ca` and `www.golfalytics.ca`
3. Vercel will give you DNS records to add
4. Go to your domain registrar (GoDaddy, Namecheap, etc.)
5. Add the DNS records Vercel provides:
   - A record: `76.76.21.21`
   - CNAME record: `cname.vercel-dns.com`
6. Wait 5-30 minutes for DNS propagation
7. Your site will be live at golfalytics.ca

## File Structure Overview

```
golfalytics-site/
├── index.html          # Main landing page
├── privacy.html        # Privacy policy
├── styles.css          # All styling
├── script.js           # Interactions & form handling
├── vercel.json         # Vercel configuration
├── package.json        # Project info
├── .gitignore          # Git ignore rules
├── README.md           # Documentation
└── DEPLOYMENT.md       # This file
```

## Key Features Implemented

### ✅ Responsive Design
- Mobile-first approach
- Works on all screen sizes
- Optimized for phones, tablets, desktops

### ✅ Golf-Specific Content
- All arena references changed to golf courses
- Golfer-focused messaging
- Golf industry terminology

### ✅ Privacy-Compliant Messaging
- Privacy policy page
- Compliant data handling language
- Anonymization emphasis

### ✅ Contact Form
- Multi-option interest selector
- Validation included
- Ready for backend integration

### ✅ SEO Ready
- Semantic HTML
- Meta descriptions
- Fast loading

## Connecting a Form Backend

The form currently prevents default submission. To make it functional:

### Option A: Formspree (Easiest)

1. Go to https://formspree.io
2. Create a free account
3. Create a new form
4. Copy your form endpoint
5. In `index.html`, find the `<form>` tag and add:
   ```html
   <form action="https://formspree.io/f/YOUR_FORM_ID" method="POST">
   ```

### Option B: Netlify Forms

1. Add `data-netlify="true"` to your form tag
2. Deploy to Netlify instead of Vercel
3. Forms are automatically handled

### Option C: Custom Backend

1. Create an API endpoint (Node.js, Python, etc.)
2. Update the form submit handler in `script.js`
3. Send form data to your API

## Adding Analytics

### Google Analytics

Add to `<head>` in `index.html`:

```html
<!-- Google tag (gtag.js) -->
<script async src="https://www.googletagmanager.com/gtag/js?id=G-XXXXXXXXXX"></script>
<script>
  window.dataLayer = window.dataLayer || [];
  function gtag(){dataLayer.push(arguments);}
  gtag('js', new Date());
  gtag('config', 'G-XXXXXXXXXX');
</script>
```

### Vercel Analytics

1. In Vercel project → Analytics → Enable
2. Analytics automatically added (no code needed)

## Customization Tips

### Change Colors

Edit CSS variables in `styles.css`:

```css
:root {
    --primary-color: #2d5016;      /* Dark green */
    --secondary-color: #4a7c1f;    /* Medium green */
    --accent-color: #7ab800;       /* Bright green */
}
```

### Update Stats

Edit in `index.html` (Stats Bar section):

```html
<div class="stat-number">700+</div>
<div class="stat-label">Golf Courses</div>
```

### Modify Case Study

Find the case study section in `index.html` and update:
- The 1.8× multiplier
- The description text
- The CTA button

## Troubleshooting

### Site not deploying?
- Check that all files are committed to GitHub
- Verify the repository is public (or Vercel has access)
- Check Vercel deployment logs for errors

### Custom domain not working?
- Verify DNS records are correct
- Wait up to 24 hours for DNS propagation
- Check domain registrar nameservers

### Form not submitting?
- Check browser console for JavaScript errors
- Verify form action is set correctly
- Test with a form service like Formspree

## Next Steps

1. ✅ Deploy to Vercel
2. ✅ Test on mobile and desktop
3. ✅ Connect form backend
4. ✅ Add custom domain
5. ✅ Set up analytics
6. ✅ Create blog content (optional)
7. ✅ Add case studies
8. ✅ Build report product pages

## Support

Need help? Contact:
- Measured Reporting: info@mearep.com
- Documentation: See README.md

---

**Pro Tips:**

- Vercel provides automatic HTTPS (SSL certificate)
- Deploys happen automatically when you push to GitHub
- Use Vercel's preview deployments to test changes
- Keep the design clean and focused on conversion

Good luck with your launch! 🏌️
