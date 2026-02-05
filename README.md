# Artifit

All-in-one client portal for The Fit Clinic.

## 🌐 Live Site

**https://artifit.fitclinic.io**

## Current Status

The previous placeholder portal has been rolled back. A minimal maintenance page is currently deployed while the new client portal is prepared.

## 📦 Deployment

The site deploys automatically to GitHub Pages via GitHub Actions on every push to `main`.

- Custom domain: `artifit.fitclinic.io`
- Source: GitHub Actions workflow (`.github/workflows/deploy.yml`)
- DNS documentation: [DNS_SETUP.md](DNS_SETUP.md)

## Adding the New Portal

To deploy the updated React/Vite client portal:

1. Replace `index.html` and add project files (`package.json`, `vite.config.js`, `tailwind.config.js`, `postcss.config.js`, `src/` directory)
2. Update the deploy workflow to include a build step (`npm ci && npm run build`)
3. Push to `main` — GitHub Actions will build and deploy automatically

## 📝 Repository Settings

Ensure the following are configured in GitHub:

1. Settings → Pages → Source: **GitHub Actions**
2. Settings → Pages → Custom domain: **artifit.fitclinic.io**
3. Settings → Pages → Enforce HTTPS: ✓
