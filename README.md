# Artifit
All in one client resource for The Fit Clinic

## 🌐 Live Site
Visit the interactive portal at: **https://artifit.fitclinic.io**

## 📦 Deployment

This project is automatically deployed to GitHub Pages using GitHub Actions. The deployment workflow runs on every push to the `main` branch.

### GitHub Pages Setup
1. The site is hosted on GitHub Pages
2. Custom domain: `artifit.fitclinic.io`
3. Automatic deployment via GitHub Actions workflow

### DNS Configuration

To route the custom domain `artifit.fitclinic.io` to GitHub Pages, configure the following DNS records at your DNS provider:

#### Option 1: Using A Records (Recommended)
Add the following A records for `artifit.fitclinic.io`:
```
185.199.108.153
185.199.109.153
185.199.110.153
185.199.111.153
```

#### Option 2: Using CNAME Record
If using a subdomain, add a CNAME record:
```
artifit.fitclinic.io -> fitanon.github.io
```

### DNS Setup Steps
1. Log in to your DNS provider (e.g., Cloudflare, GoDaddy, Route53)
2. Navigate to DNS settings for `fitclinic.io`
3. Add one of the following:
   - **A Records**: Point `artifit` subdomain to GitHub Pages IPs (185.199.108-111.153)
   - **CNAME Record**: Point `artifit` subdomain to `fitanon.github.io`
4. Wait for DNS propagation (can take up to 48 hours, usually much faster)
5. Verify by visiting https://artifit.fitclinic.io

### Enabling HTTPS
GitHub Pages automatically provides free HTTPS with Let's Encrypt once:
1. DNS records are properly configured
2. DNS propagation is complete
3. You enable "Enforce HTTPS" in repository Settings > Pages

## 🚀 Features

The interactive portal includes:
- 📊 Workout counter with local storage persistence
- 💪 Feature cards for various fitness services
- 🎨 Modern, responsive design
- ✨ Interactive elements with smooth animations

## 🛠️ Development

To run locally:
1. Clone the repository
2. Open `index.html` in a web browser
3. No build process required - pure HTML/CSS/JavaScript

## 📝 Repository Settings

Ensure the following settings are configured in GitHub:
1. Go to Settings > Pages
2. Source: GitHub Actions
3. Custom domain: `artifit.fitclinic.io`
4. Enforce HTTPS: ✓ (enable after DNS is configured)

## 🔄 Updating the Site

1. Make changes to `index.html` or other files
2. Commit and push to the `main` branch
3. GitHub Actions will automatically deploy the changes
4. Changes will be live in a few minutes
