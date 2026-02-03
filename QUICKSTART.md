# Quick Start Guide

## 🚀 Getting Started with Artifit

This guide will help you get the Artifit interactive portal up and running at `artifit.fitclinic.io` in just a few steps.

## Overview

Artifit is an interactive client resource portal for The Fit Clinic, automatically deployed to GitHub Pages with a custom domain.

## What's Included

✅ **Interactive HTML Portal** - A modern, responsive client portal with:
- Workout counter with local storage
- Feature cards for fitness services
- Smooth animations and modern design
- Mobile-responsive layout

✅ **Automated Deployment** - GitHub Actions workflow that:
- Deploys on every push to `main` branch
- Can be triggered manually
- Uses official GitHub Pages actions

✅ **Custom Domain Support** - Pre-configured for `artifit.fitclinic.io`

✅ **Comprehensive Documentation** - Includes DNS setup and troubleshooting guides

## Prerequisites

Before you begin, ensure you have:
- [ ] Admin access to the GitHub repository
- [ ] Access to DNS management for `fitclinic.io` domain
- [ ] GitHub Pages enabled for the repository

## Setup Steps

### Step 1: Enable GitHub Pages (One-time setup)

1. Go to repository **Settings** → **Pages**
2. Under "Build and deployment":
   - **Source**: Select `GitHub Actions`
3. Under "Custom domain":
   - Enter: `artifit.fitclinic.io`
   - Click **Save**
4. Wait for DNS check (will be pending until Step 2 is complete)

### Step 2: Configure DNS

Choose one of the following methods:

#### Method A: Using A Records (Recommended)

Add these A records to your DNS provider for `artifit.fitclinic.io`:
- 185.199.108.153
- 185.199.109.153
- 185.199.110.153
- 185.199.111.153

#### Method B: Using CNAME

Add a CNAME record pointing `artifit.fitclinic.io` to `fitanon.github.io`

**For detailed DNS instructions**, see [DNS_SETUP.md](DNS_SETUP.md)

### Step 3: Wait for DNS Propagation

- DNS changes can take 5 minutes to 48 hours to propagate
- Usually completes within 1-2 hours
- Check status at: https://www.whatsmydns.net

### Step 4: Enable HTTPS

Once DNS is configured and propagated:
1. Go to repository **Settings** → **Pages**
2. Check the box for **Enforce HTTPS**
3. GitHub will automatically provision an SSL certificate

### Step 5: Deploy

The site will automatically deploy when you:
1. Merge changes to the `main` branch, OR
2. Manually trigger the workflow from **Actions** tab

### Step 6: Verify

Visit `https://artifit.fitclinic.io` to see your live site! 🎉

## Making Changes

To update the site:

1. Edit `index.html` or create new files
2. Commit and push to `main` branch
3. GitHub Actions will automatically deploy (takes ~2-3 minutes)
4. Refresh your browser to see changes

## File Structure

```
Artifit/
├── index.html              # Main interactive portal page
├── CNAME                   # Custom domain configuration
├── README.md               # Project documentation
├── DNS_SETUP.md           # Detailed DNS setup guide
├── QUICKSTART.md          # This file
├── .gitignore             # Git ignore rules
└── .github/
    └── workflows/
        └── deploy.yml      # GitHub Actions deployment workflow
```

## Common Tasks

### Update the Portal Content
Edit `index.html` and push to `main` branch

### Change Custom Domain
1. Update `CNAME` file with new domain
2. Update DNS records
3. Update in GitHub Settings → Pages

### Manual Deployment
1. Go to **Actions** tab
2. Select "Deploy to GitHub Pages" workflow
3. Click **Run workflow**

### View Deployment Status
1. Go to **Actions** tab
2. See latest workflow runs and their status
3. Click on a run to see detailed logs

## Troubleshooting

### Site Not Loading
- Verify DNS records are correct
- Wait for DNS propagation
- Check GitHub Actions for deployment errors
- Ensure Pages is enabled in Settings

### HTTPS Not Working
- Ensure DNS is fully propagated
- Enable "Enforce HTTPS" in Settings → Pages
- Wait a few minutes for certificate provisioning

### Changes Not Showing
- Check that workflow ran successfully in Actions tab
- Clear browser cache (Ctrl+F5 or Cmd+Shift+R)
- Wait a few minutes for CDN cache to clear

## Next Steps

- Customize `index.html` with your content
- Add more pages to the site
- Configure additional features
- Review [README.md](README.md) for detailed documentation

## Support Resources

- [GitHub Pages Documentation](https://docs.github.com/en/pages)
- [DNS Setup Guide](DNS_SETUP.md)
- [Repository Settings](https://github.com/fitanon/Artifit/settings)
- [GitHub Actions Logs](https://github.com/fitanon/Artifit/actions)

---

**Need Help?** Check the troubleshooting sections in [README.md](README.md) and [DNS_SETUP.md](DNS_SETUP.md)
