# Customization Guide - Business Landing Template

This guide explains how to customize the template for your specific business needs.

## Quick Start

```bash
git clone https://github.com/CastelDazur/business-landing-template.git my-landing
cd my-landing
npm install
npm run dev
```

## Configuration

All customizable variables are in `config.js`:

```javascript
// config.js
module.exports = {
  // Company information
  company: {
    name: 'Your Company Name',
    tagline: 'Your compelling tagline here',
    phone: '+33 6 XX XX XX XX',
    email: 'contact@yourcompany.com',
    address: 'Your address, City, France',
    siret: '12345678901234', // Optional
  },

  // Hero section
  hero: {
    title: 'Main Headline',
    subtitle: 'Supporting text that explains your value proposition',
    ctaText: 'Get a Free Quote',
    ctaPhone: '+33 6 XX XX XX XX',
    backgroundImage: './assets/hero-bg.jpg',
  },

  // Services (shown as cards)
  services: [
    {
      icon: 'truck',
      title: 'Service 1',
      description: 'Brief description of the service',
      price: 'From €99/day',
    },
    // Add more services...
  ],

  // SEO
  seo: {
    title: 'Your Business - City | Service Type',
    description: 'Meta description for search engines (150-160 chars)',
    keywords: ['keyword1', 'keyword2', 'city', 'service'],
    ogImage: './assets/og-image.jpg',
  },

  // Google Analytics (optional)
  analytics: {
    googleAnalyticsId: 'G-XXXXXXXXXX',
  },

  // Contact form
  contactForm: {
    submitEndpoint: '/api/contact', // Your form handler endpoint
    successMessage: 'Thank you! We will contact you within 2 hours.',
  },
};
```

## Color Scheme

Edit `assets/css/variables.css` to change the color palette:

```css
:root {
  --color-primary: #2563eb;      /* Main brand color */
  --color-primary-dark: #1d4ed8; /* Hover state */
  --color-accent: #f59e0b;       /* CTA buttons, highlights */
  --color-text: #111827;         /* Body text */
  --color-text-muted: #6b7280;   /* Secondary text */
  --color-bg: #ffffff;           /* Background */
  --color-bg-alt: #f9fafb;       /* Alternate sections */
  --color-border: #e5e7eb;       /* Borders, dividers */
}
```

## Sections

The template includes these sections (toggle in `config.js`):

| Section | Description | Required |
|---------|-------------|----------|
| `hero` | Full-width hero with CTA | Yes |
| `services` | Service cards grid | Yes |
| `about` | Company story + photo | Recommended |
| `gallery` | Photo gallery | Optional |
| `testimonials` | Customer reviews | Recommended |
| `coverage` | Service area map | Optional |
| `faq` | Expandable FAQ | Recommended |
| `contact` | Contact form + map | Yes |
| `footer` | Links + legal | Yes |

## Adding Images

1. Place images in `assets/images/`
2. Recommended sizes:
   - Hero background: `1920x1080px` (JPG, <200KB)
   - Service icons: `64x64px` (SVG preferred)
   - Gallery photos: `800x600px` (JPG, <150KB)
   - Team photos: `400x400px` (JPG)
   - OG image: `1200x630px` (JPG)

## SEO Checklist

- [ ] Set unique title with city + service keywords
- [ ] Write meta description (150-160 chars)
- [ ] Add Google Analytics
- [ ] Submit sitemap to Google Search Console
- [ ] Add Google My Business link
- [ ] Add schema.org LocalBusiness markup (already included)

## Deployment

### Static hosting (Netlify/Vercel)
```bash
npm run build
# Deploy the /dist folder
```

### VPS/Dedicated server
```bash
npm run build
# Serve /dist with Nginx
```

Sample Nginx config is in `deploy/nginx.conf`.

## Used in Production

This template powers [locationbatiprofit.com](https://locationbatiprofit.com) - 
construction equipment rental in Côte d'Azur, France.

## Support

Open an issue or contact: [casteldazur@gmail.com](mailto:casteldazur@gmail.com)
