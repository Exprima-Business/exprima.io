# Exprima.io Deployment Guide

Quick-start guide for deploying Exprima site to GitHub Pages.

## Prerequisites

- GitHub account (for Exprima organization or personal)
- Domain registrar access (for exprima.io DNS configuration)
- Git installed locally (optional - can use GitHub web interface)

## Deployment Steps

### Step 1: GitHub Account Structure (IMPORTANT)

**Recommended Approach: Organization + Personal Account**

1. **Personal Account:** `elliottmattice`
   - For: elliottmattice.work (personal brand)
   - Repository: `elliottmattice.github.io`

2. **Organization:** `Exprima` (owned by elliottmattice account)
   - For: exprima.io (business)
   - Repository: `Exprima.github.io`

**Create Organization:**
- Log into `elliottmattice` GitHub account
- Click profile → "Your organizations"
- "New organization"
- Name: `Exprima`
- Free plan
- Create

**Why this structure:**
- ✅ ToS compliant (one personal + unlimited organizations)
- ✅ Clean brand separation
- ✅ Automatic GitHub Pages deployment
- ✅ Professional structure

### Step 2: Create Repository

**Option A: Organization Repository (Recommended)**

1. Log into GitHub as organization owner
2. Go to organization: `github.com/Exprima`
3. Click "New repository"
4. **Repository name:** `Exprima.github.io` (EXACT - case sensitive)
5. **Public** (required for free GitHub Pages)
6. **DO NOT** initialize with README
7. Create repository

**Option B: Personal Repository**

1. Repository name: Any name
2. Public
3. Don't initialize with README
4. Create repository

### Step 3: Upload Site Files

**Method 1: GitHub Web Interface (Easiest)**

1. Navigate to repository
2. Click "uploading an existing file"
3. Drag entire `exprima-site` folder contents
4. **Do NOT upload the parent folder, upload contents:**
   - `_config.yml` ✓
   - `_layouts/` ✓
   - `index.html` ✓
   - All other files ✓
5. Commit message: "Initial Exprima site deployment"
6. Commit

**Method 2: Git Command Line**

```bash
# Navigate to extracted site folder
cd /path/to/exprima-site

# Initialize git
git init

# Add all files
git add .

# Commit
git commit -m "Initial Exprima site deployment"

# Add remote (Organization repository)
git remote add origin https://github.com/Exprima/Exprima.github.io.git

# OR add remote (Personal repository)
git remote add origin https://github.com/elliottmattice/exprima-site.git

# Push to main branch
git branch -M main
git push -u origin main
```

### Step 4: Enable GitHub Pages

**For Organization Repository (`Exprima.github.io`):**
- GitHub Pages automatically enabled
- Site live at: `https://Exprima.github.io`
- Wait 2-3 minutes for first deployment

**For Other Repository Names:**
1. Go to repository Settings
2. Click "Pages" (left sidebar)
3. Source: "Deploy from a branch"
4. Branch: `main`, Folder: `/ (root)`
5. Save
6. Wait 2-3 minutes
7. Site live at: `https://[username].github.io/[repo-name]`

### Step 5: Configure Custom Domain (exprima.io)

**Part A: GitHub Settings**

1. Repository → Settings → Pages
2. Custom domain field: `exprima.io`
3. Save
4. Wait for DNS check (may take a few minutes)

**Part B: DNS Configuration (Dreamhost or Domain Registrar)**

**CNAME Record (for www subdomain):**
```
Type: CNAME
Name: www
Value: Exprima.github.io
TTL: 3600 (or default)
```

**A Records (for apex domain @):**
```
Type: A
Name: @ (or leave blank for apex)
Value: 185.199.108.153

Type: A
Name: @
Value: 185.199.109.153

Type: A
Name: @
Value: 185.199.110.153

Type: A
Name: @
Value: 185.199.111.153
```

**DNS Propagation:**
- Wait 15-60 minutes for DNS to propagate
- Check status: `dig exprima.io` or online DNS checker

**Part C: Enable HTTPS**

1. Return to GitHub → Settings → Pages
2. Wait for "DNS check successful" message
3. Check "Enforce HTTPS"
4. SSL certificate provisions automatically (15-30 minutes)

**Final Result:**
- `http://exprima.io` → redirects to `https://exprima.io`
- `http://www.exprima.io` → redirects to `https://exprima.io`

### Step 6: Verify Deployment

**Check these URLs:**
- `https://Exprima.github.io` (should redirect to exprima.io if custom domain set)
- `https://exprima.io`
- `https://www.exprima.io`
- `https://exprima.io/services/`
- `https://exprima.io/platform/`
- `https://exprima.io/about/`

**Visual checks:**
- ✓ Navigation works
- ✓ Grain texture visible
- ✓ All links functional
- ✓ Responsive design (test mobile)
- ✓ Footer contact info correct

## Pre-Launch Customization

**Before making site public, update:**

### 1. Add Founder Photo

```bash
# Add image file
assets/images/elliott-mattice.jpg

# Edit about.md, replace placeholder div with:
<img src="/assets/images/elliott-mattice.jpg" 
     alt="Elliott Mattice" 
     style="width: 100%; height: 100%; object-fit: cover; border-radius: 6px;">
```

### 2. Verify Contact Information

Check these files contain correct contact details:
- `_config.yml` (company info)
- `index.html` (contact section)
- Footer in `_layouts/default.html`

### 3. Update Calendly Links

Search all files for: `calendly.com/elliott-mattice-exprima/30min`

Replace with your actual scheduling link in:
- `index.html`
- `services.md`
- `platform.md`
- `about.md`

### 4. Verify External Links

- `elliottmattice.work` → Check all links point to correct URLs
- LinkedIn profile
- YouTube channel (@upstreamrisk)

## Post-Deployment

### Testing Checklist

- [ ] Homepage loads correctly
- [ ] All service pages accessible
- [ ] Platform page renders
- [ ] About page shows founder info
- [ ] Navigation links work
- [ ] Footer links functional
- [ ] Contact buttons/links work
- [ ] Mobile responsive design works
- [ ] HTTPS enabled and working
- [ ] No broken images
- [ ] Grain texture visible

### Monitoring

**GitHub Pages Build Status:**
- Repository → Actions tab
- Shows deployment status
- Build errors appear here

**Analytics (Optional):**
- Add Google Analytics in `_layouts/default.html` `<head>` section
- Track visitor metrics

## Updating Content

### Making Changes

**Method 1: GitHub Web Interface**
1. Navigate to file in repository
2. Click pencil icon (Edit)
3. Make changes
4. Commit changes
5. Wait 2-3 minutes for rebuild

**Method 2: Local Development**
```bash
# Make changes locally
# Test with: bundle exec jekyll serve

# Commit and push
git add .
git commit -m "Update [description]"
git push origin main

# GitHub Pages rebuilds automatically
```

### Common Updates

**Update service pricing:**
- Edit `services.md`

**Add new tool/platform info:**
- Edit `platform.md`

**Update track record metrics:**
- Edit `index.html` (metrics section)
- Edit `about.md` (track record section)

**Change color scheme:**
- Edit CSS variables in `_layouts/default.html`

## Troubleshooting

### Site Not Loading

**Check:**
1. GitHub Pages enabled in Settings
2. Repository is public
3. Branch is `main` and folder is `/ (root)`
4. Wait 2-3 minutes after push for rebuild

**Build Status:**
- Check repository → Actions for errors
- Look for failed builds

### Custom Domain Not Working

**Check:**
1. CNAME file exists in repository root
2. Contains only: `exprima.io`
3. DNS records configured correctly:
   ```bash
   dig exprima.io
   # Should show GitHub Pages IP addresses
   
   dig www.exprima.io
   # Should show CNAME to Exprima.github.io
   ```
4. Wait 1-2 hours for DNS propagation

### HTTPS Not Working

**Check:**
1. DNS propagated (use dig/nslookup)
2. "Enforce HTTPS" checked in Settings → Pages
3. Certificate provisioning complete (can take 15-30 min)
4. Clear browser cache

### Broken Links

**Check:**
1. Case sensitivity (GitHub Pages is case-sensitive)
2. File extensions correct (.md becomes .html in URLs)
3. Leading slashes for root paths: `/services/` not `services/`

## Maintenance

### Regular Updates

**Monthly:**
- Review contact information
- Check external links still valid
- Update track record if new achievements

**As Needed:**
- Add blog posts to `_posts/`
- Update services/pricing
- Add new tools/platforms
- Refresh founder bio

### Backup

**Keep local copy:**
```bash
git clone https://github.com/Exprima/Exprima.github.io.git
```

**Export from GitHub:**
- Settings → bottom of sidebar
- "Export repository"

## Support Resources

**GitHub Pages:**
- Documentation: https://docs.github.com/en/pages
- Status: https://www.githubstatus.com/

**Jekyll:**
- Documentation: https://jekyllrb.com/docs/
- Liquid syntax: https://shopify.github.io/liquid/

**DNS Tools:**
- DNS Checker: https://dnschecker.org/
- Dig web interface: https://toolbox.googleapps.com/apps/dig/

## Success Criteria

Site successfully deployed when:
- ✅ `https://exprima.io` loads homepage
- ✅ All navigation links work
- ✅ Design matches screenshots
- ✅ Contact information correct
- ✅ Links to elliottmattice.work functional
- ✅ Mobile responsive
- ✅ HTTPS enabled
- ✅ No console errors
- ✅ Load time < 2 seconds

**You're ready to launch! 🚀**
