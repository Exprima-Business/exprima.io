# Exprima.io - Jekyll Site

Professional business website for Exprima, applying Upstream Risk Translation methodology to security and governance services.

## Site Overview

**Live URL:** https://exprima.io  
**Platform:** Jekyll 4.3 + GitHub Pages  
**Design:** Professional business aesthetic with grain texture overlay

## Directory Structure

```
exprima-site/
├── _config.yml              # Site configuration
├── _layouts/                
│   ├── default.html         # Main layout with navigation & footer
│   └── page.html            # Page layout for static content
├── index.html               # Homepage
├── services.md              # Services page
├── platform.md              # Platform & Tools page
├── about.md                 # About Exprima page
├── _posts/                  # Future blog posts (optional)
├── _drafts/                 # Draft content (not published)
├── assets/
│   ├── css/                 # (Empty - CSS inline in layouts)
│   ├── images/              # Site images
│   └── pdfs/                # Downloadable resources
├── Gemfile                  # Ruby dependencies
└── CNAME                    # Custom domain configuration
```

## Content Pages

### Homepage (index.html)
- Hero section with value proposition
- Core services overview (4 service cards)
- Methodology explanation (3 Upstream Risk Translation frameworks)
- Platform & tools overview
- Track record metrics
- Contact section

### Services Page (services.md)
1. **Fractional Security Executive** - Strategic leadership, 2-4 days/month
2. **AI Security & Governance** - Complete AI governance programs
3. **Compliance Program Architecture** - CMMC, FedRAMP, HIPAA, SOC2, PCI-DSS
4. **Strategic Risk Advisory** - Executive counsel on complex decisions

### Platform Page (platform.md)
1. **Clause Atlas** (Proprietary) - AI regulatory scanning engine
2. **Proposal Atlas** (Proprietary) - Multi-model AI proposal generation
3. **ZeroTrusted.ai Platform** (Partner) - Enterprise AI governance

### About Page (about.md)
- Company overview
- Founder bio (Elliott Mattice)
- Methodology foundation
- Track record
- Operating principles

## Design System

### Colors
- **Primary:** Navy/teal (#1a5f7a, #2d8ba8, #0d3d52)
- **Accent:** #57a6c1
- **Backgrounds:** Dark theme (black to gray-900)
- **Text:** Gray-100 (primary), Gray-300 (secondary), Gray-400 (muted)

### Typography
- **Display/Body:** Inter (300-700 weights)
- **Monospace:** IBM Plex Mono (400-600 weights)
- **Font rendering:** Antialiased, optimizeLegibility

### Design Elements
- Grain texture overlay (JavaScript-generated, 3% opacity)
- Border-left card pattern (3px solid primary)
- Professional business tone (no "I" language)
- Sticky navigation with backdrop blur
- Responsive breakpoint: 768px

## Content Guidelines

### Tone & Voice
- **Professional business language** (not personal consulting)
- **Third-person perspective** ("Exprima provides" not "I provide")
- **Results-focused** (metrics, outcomes, track record)
- **Methodology-driven** (Upstream Risk Translation frameworks central)

### Brand Integration
- **Upstream Risk Translation** mentioned prominently
- **Links to elliottmattice.work** for framework documentation
- **Founded by Elliott Mattice** (creator of methodology)
- **Tools positioned as enhancers** (not replacement for expertise)

## Local Development

### Prerequisites
- Ruby 2.7+ installed
- Bundler gem installed

### Setup
```bash
# Install dependencies
bundle install

# Run local server
bundle exec jekyll serve

# View site
open http://localhost:4000
```

### Build Site
```bash
bundle exec jekyll build
# Output in _site/ directory
```

## GitHub Pages Deployment

### Option 1: Organization Repository (Recommended)

**Repository name:** `Exprima.github.io` (if using organization account)

**Steps:**
1. Create organization "Exprima" on GitHub
2. Create repository: `Exprima.github.io`
3. Push this site to main branch
4. GitHub Pages automatically deploys
5. Site live at: `https://Exprima.github.io`

### Option 2: Custom Repository

**Repository name:** Any name (e.g., `exprima-site`)

**Steps:**
1. Create repository
2. Push code to main branch
3. Go to Settings → Pages
4. Source: Deploy from branch `main`, folder `/ (root)`
5. Save
6. Site live at: `https://[username].github.io/exprima-site`

### Custom Domain Setup (exprima.io)

**Already configured via CNAME file in repository.**

**DNS Configuration (in Dreamhost or domain registrar):**
```
CNAME Record:
  Name: www
  Value: Exprima.github.io (or [username].github.io)

A Records (for apex domain):
  Name: @
  Value: 185.199.108.153
  
  Name: @
  Value: 185.199.109.153
  
  Name: @
  Value: 185.199.110.153
  
  Name: @
  Value: 185.199.111.153
```

**In GitHub Repository Settings:**
1. Go to Settings → Pages
2. Custom domain: `exprima.io`
3. Save
4. Wait 15-60 minutes for DNS propagation
5. Enable "Enforce HTTPS" once certificate provisions

## Customization

### Update Contact Information

**In `_config.yml`:**
```yaml
company:
  phone: "(202) 262-4088"
  email: contact@exprima.io
  address: "1311 Park St, #1164, Alameda, CA 94501"
```

### Add Founder Photo

1. Add headshot image: `assets/images/elliott-mattice.jpg`
2. Update in `about.md`:
```html
<div class="founder-photo">
    <img src="/assets/images/elliott-mattice.jpg" alt="Elliott Mattice" style="width: 100%; height: 100%; object-fit: cover; border-radius: 6px;">
</div>
```

### Update Calendly Link

Replace `https://calendly.com/elliott-mattice-exprima/30min` with actual scheduling link in:
- `index.html` (2 locations)
- `services.md`
- `platform.md`
- `about.md`

### Change Color Scheme

Edit CSS variables in `_layouts/default.html`:
```css
:root {
    --slate-primary: #3b5998;  /* Change primary color */
    --slate-light: #4a6bb3;    /* Change light accent */
    --slate-dark: #2c4373;     /* Change dark accent */
}
```

## Content Updates

### Adding Blog Posts (Optional)

Create file in `_posts/` with format: `YYYY-MM-DD-title.md`

```yaml
---
layout: post
title: "Post Title"
date: YYYY-MM-DD
category: analysis
excerpt: "Brief description"
---

Post content here...
```

### Creating Drafts

Add files to `_drafts/` folder (no date in filename)
```bash
# Preview drafts locally
bundle exec jekyll serve --drafts
```

## Maintenance

### Updating Dependencies
```bash
bundle update
```

### Testing Before Deploy
```bash
# Build and test locally
bundle exec jekyll serve

# Check for broken links
# Verify all pages render correctly
# Test responsive design
```

### Deployment Checklist
- [ ] All placeholder text replaced
- [ ] Contact information verified
- [ ] Founder photo added
- [ ] Calendly links updated
- [ ] Links to elliottmattice.work verified
- [ ] Test all navigation links
- [ ] Verify responsive design (mobile)
- [ ] Check grain texture renders
- [ ] Confirm color scheme

## Support

### Jekyll Documentation
- Official Docs: https://jekyllrb.com/docs/
- GitHub Pages: https://docs.github.com/en/pages

### Troubleshooting

**Build fails:**
- Check `Gemfile` dependencies
- Verify Jekyll version compatibility
- Review `_config.yml` syntax

**Site not updating:**
- GitHub Pages can take 2-3 minutes to rebuild
- Check repository Settings → Pages for build status
- Clear browser cache

**Custom domain not working:**
- Verify DNS records propagated (use dig or nslookup)
- Check CNAME file contains correct domain
- Ensure GitHub Pages settings show custom domain

## Integration with Brand Ecosystem

**Personal Brand (elliottmattice.work):**
- Teaches Upstream Risk Translation methodology
- Framework documentation
- Thought leadership content
- Links to exprima.io for implementation

**Business (exprima.io):**
- Applies Upstream Risk Translation
- Fractional executive services
- AI-powered tools
- Links to elliottmattice.work for methodology

**Both channels share:**
- Same methodology foundation
- Consistent branding
- Cross-promotion strategy
- Integrated customer journey

## License

© 2026 Exprima. All rights reserved.
Methodology by Elliott Mattice (Upstream Risk Translation).
#   e x p r i m a . i o  
 