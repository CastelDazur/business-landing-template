# Customization Guide

How to adapt this business landing page template for your own brand or project.

## Quick Setup (5 minutes)

### 1. Clone the repository

```bash
git clone https://github.com/CastelDazur/business-landing-template.git my-landing
cd my-landing
```

### 2. Configure your brand

Edit `config/site.config.js`:

```javascript
module.exports = {
  // Brand identity
  siteName: 'Your Company Name',
  tagline: 'Your compelling tagline here',
  description: 'One-sentence description for SEO meta tags',
  logo: '/assets/logo.svg',
  favicon: '/assets/favicon.ico',

  // Contact & Location
  phone: '+33 6 00 00 00 00',
  email: 'contact@yourcompany.com',
  address: '123 Rue de la Paix, 06000 Nice, France',
  googleMapsUrl: 'https://maps.google.com/?q=...',

  // Social media
  social: {
    linkedin: 'https://linkedin.com/company/yourcompany',
    instagram: 'https://instagram.com/yourcompany',
    facebook: 'https://facebook.com/yourcompany',
    twitter: 'https://twitter.com/yourcompany',
  },

  // SEO
  seo: {
    keywords: ['keyword1', 'keyword2', 'keyword3'],
    ogImage: '/assets/og-image.jpg',
    twitterCard: 'summary_large_image',
  },
};
```

---

## Color Scheme

Edit `assets/css/variables.css`:

```css
:root {
  /* Primary brand colors */
  --color-primary: #2563eb;       /* Main CTA color */
  --color-primary-dark: #1d4ed8;  /* Hover state */
  --color-primary-light: #dbeafe; /* Backgrounds, highlights */

  /* Secondary palette */
  --color-secondary: #7c3aed;
  --color-accent: #f59e0b;

  /* Neutral */
  --color-text: #1f2937;
  --color-text-muted: #6b7280;
  --color-bg: #ffffff;
  --color-bg-alt: #f9fafb;
  --color-border: #e5e7eb;

  /* Typography */
  --font-heading: 'Inter', 'Helvetica Neue', sans-serif;
  --font-body: 'Inter', 'Helvetica Neue', sans-serif;
  --font-size-base: 16px;
  --line-height-base: 1.6;

  /* Spacing */
  --container-max-width: 1200px;
  --section-padding: 80px;
  --border-radius: 8px;
}
```

---

## Sections

### Hero Section

Edit `sections/hero.html`:

```html
<!-- Replace placeholder content -->
<h1 class="hero__title">
  Your Main Headline
  <span class="highlight">Key Differentiator</span>
</h1>
<p class="hero__subtitle">
  Your supporting copy that explains the value proposition
  in 1-2 sentences.
</p>
<div class="hero__cta">
  <a href="#contact" class="btn btn--primary">Get Free Quote</a>
  <a href="#services" class="btn btn--ghost">Learn More</a>
</div>
```

**Hero background options:**

```css
/* Option 1: Solid color */
.hero { background: var(--color-primary); }

/* Option 2: Gradient */
.hero { background: linear-gradient(135deg, #1e3a8a 0%, #7c3aed 100%); }

/* Option 3: Image with overlay */
.hero {
  background-image: url('/assets/hero-bg.jpg');
  background-size: cover;
  background-position: center;
}
.hero::before {
  content: '';
  background: rgba(0, 0, 0, 0.5);
}
```

### Services Section

Edit `config/services.json`:

```json
[
  {
    "icon": "🚜",
    "title": "Equipment Rental",
    "description": "Professional equipment available 24/7",
    "features": ["Feature 1", "Feature 2", "Feature 3"],
    "cta": "Request Quote",
    "ctaUrl": "#contact"
  },
  {
    "icon": "⚡",
    "title": "Fast Delivery",
    "description": "Same-day delivery in the Cote d'Azur region",
    "features": ["Feature 1", "Feature 2"],
    "cta": "Learn More",
    "ctaUrl": "/delivery"
  }
]
```

### Testimonials

Edit `config/testimonials.json`:

```json
[
  {
    "name": "Jean-Pierre Martin",
    "company": "BTP Construction SARL",
    "role": "Chef de chantier",
    "text": "Excellent service, materiel toujours en parfait etat.",
    "rating": 5,
    "avatar": "/assets/avatars/jp-martin.jpg"
  }
]
```

---

## Analytics & Tracking

Edit `config/analytics.js`:

```javascript
module.exports = {
  googleAnalytics: 'G-XXXXXXXXXX',  // GA4 Measurement ID
  googleTagManager: 'GTM-XXXXXXX',  // Optional GTM
  facebookPixel: '1234567890',       // Optional FB Pixel
  hotjar: '1234567',                  // Optional Hotjar

  // Conversion tracking
  conversions: {
    formSubmit: 'AW-XXXXXXXXXX/XXXXXX',  // Google Ads
    phoneClick: 'AW-XXXXXXXXXX/YYYYYY',
  }
};
```

---

## Deployment

### Netlify (Recommended — Free)

```bash
# Install Netlify CLI
npm install -g netlify-cli

# Deploy
netlify deploy --prod --dir=.
```

### Vercel

```bash
npm install -g vercel
vercel --prod
```

### Apache/Nginx (VPS)

Copy all files to your web server's public directory:

```bash
scp -r . user@yourserver.com:/var/www/html/
```

### GitHub Pages

1. Push to `gh-pages` branch
2. Enable GitHub Pages in repository Settings
3. Your site is live at `https://username.github.io/repo-name`

---

## SEO Optimization

1. **Meta tags** — Edit `<head>` in `index.html` with your keywords
2. **Sitemap** — Update `sitemap.xml` with your pages and last modified dates  
3. **Robots.txt** — Configure crawling rules in `robots.txt`
4. **Schema.org** — Edit `config/schema.json` for local business rich snippets
5. **Page speed** — Run `npm run optimize` to compress images and minify assets

---

*Template by [CastelDazur](https://github.com/CastelDazur) — MIT License*
