# Golfalytics

Golf course audience intelligence platform powered by Measured Reporting.

## Overview

Golfalytics provides privacy-compliant mobile foot traffic data that reveals how golfers behave — and enables you to activate, target, and measure them across digital media.

## Features

- **Audience Intelligence**: Understand golfer behaviour before and after rounds
- **Sponsorship Valuation**: Prove the commercial value of golf course audiences
- **Digital Activation**: Turn course visitation into targetable media audiences
- **Attribution & Measurement**: Close the loop on golf course marketing

## Tech Stack

- Pure HTML/CSS/JavaScript
- No dependencies or build process required
- Optimized for Vercel deployment

## Local Development

To run locally:

```bash
# Option 1: Using Python
python -m http.server 8000

# Option 2: Using Node.js
npx serve

# Then open http://localhost:8000
```

## Deployment to Vercel

### Option 1: Deploy via GitHub

1. Create a new repository on GitHub
2. Push this code to the repository:
   ```bash
   git init
   git add .
   git commit -m "Initial commit"
   git remote add origin <your-github-repo-url>
   git push -u origin main
   ```
3. Go to [vercel.com](https://vercel.com)
4. Click "New Project"
5. Import your GitHub repository
6. Vercel will automatically detect the static site
7. Click "Deploy"

### Option 2: Deploy via Vercel CLI

```bash
# Install Vercel CLI
npm i -g vercel

# Deploy
vercel

# Follow the prompts to link/create project
```

### Option 3: Deploy via Vercel Dashboard

1. Go to [vercel.com](https://vercel.com)
2. Click "Add New" → "Project"
3. Select "Import Git Repository" and connect GitHub
4. Import this repository
5. Keep default settings and deploy

## Custom Domain

After deployment, you can add a custom domain in Vercel:

1. Go to your project settings
2. Navigate to "Domains"
3. Add your custom domain (e.g., golfalytics.ca)
4. Update your DNS records as instructed

## File Structure

```
golfalytics-site/
├── index.html          # Main landing page
├── privacy.html        # Privacy policy page
├── styles.css          # All styles
├── script.js           # JavaScript functionality
├── vercel.json         # Vercel configuration
├── package.json        # Project metadata
└── README.md           # This file
```

## Customization

### Colors
The color scheme uses a golf green palette. To customize, edit the CSS variables in `styles.css`:

```css
:root {
    --primary-color: #2d5016;
    --secondary-color: #4a7c1f;
    --accent-color: #7ab800;
}
```

### Content
All content can be edited directly in `index.html`. The structure follows the Arenalytics template but is optimized for golf course marketing.

### Form Handling
The contact form currently uses JavaScript to prevent default submission. To connect it to a backend:

1. Add a form action endpoint in `index.html`
2. Or integrate with services like:
   - Formspree
   - Netlify Forms
   - Custom API endpoint

## Analytics

To add analytics, include your tracking code in the `<head>` section of `index.html`:

```html
<!-- Google Analytics -->
<script async src="https://www.googletagmanager.com/gtag/js?id=GA_MEASUREMENT_ID"></script>

<!-- Or other analytics platforms -->
```

## Performance

The site is optimized for performance:
- ✅ No dependencies
- ✅ Minimal JavaScript
- ✅ Optimized CSS
- ✅ Static files only
- ✅ Fast load times

## Browser Support

Supports all modern browsers:
- Chrome/Edge (latest 2 versions)
- Firefox (latest 2 versions)
- Safari (latest 2 versions)

## License

© 2026 Golfalytics / Measured Reporting. All rights reserved.

## Support

For questions or support, contact:
- Email: info@mearep.com
- Web: https://mearep.com
