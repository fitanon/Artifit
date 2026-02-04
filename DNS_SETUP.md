# DNS Setup Guide for Artifit.fitclinic.io

This guide will help you configure DNS records to route `artifit.fitclinic.io` to the GitHub Pages site.

## Prerequisites
- Access to DNS management for `fitclinic.io` domain
- The GitHub repository must have Pages enabled with the custom domain configured

## Step-by-Step Instructions

### 1. Access Your DNS Provider
Log in to your DNS provider's control panel. Common providers include:
- Cloudflare
- GoDaddy
- Namecheap
- AWS Route53
- Google Cloud DNS

### 2. Configure DNS Records

You have two options for configuring DNS:

#### Option A: Using A Records (Recommended for apex/root subdomains)

Add these A records for the `artifit` subdomain:

| Type | Name/Host | Value/Points to | TTL |
|------|-----------|-----------------|-----|
| A | artifit | 185.199.108.153 | Auto/3600 |
| A | artifit | 185.199.109.153 | Auto/3600 |
| A | artifit | 185.199.110.153 | Auto/3600 |
| A | artifit | 185.199.111.153 | Auto/3600 |

#### Option B: Using CNAME Record (Alternative)

Add this CNAME record:

| Type | Name/Host | Value/Points to | TTL |
|------|-----------|-----------------|-----|
| CNAME | artifit | fitanon.github.io | Auto/3600 |

**Note:** CNAME is simpler but may have slight limitations in some DNS configurations.

### 3. GitHub Repository Configuration

1. Navigate to your GitHub repository: `https://github.com/fitanon/Artifit`
2. Go to **Settings** → **Pages**
3. Under "Build and deployment":
   - Source: Select **GitHub Actions**
4. Under "Custom domain":
   - Enter: `artifit.fitclinic.io`
   - Click **Save**
5. Wait for DNS check to complete (may show pending initially)
6. Once DNS is verified, check **Enforce HTTPS**

### 4. Verify DNS Configuration

You can verify your DNS records using command line tools:

```bash
# Check A records
dig artifit.fitclinic.io A

# Check CNAME record
dig artifit.fitclinic.io CNAME

# Alternative using nslookup
nslookup artifit.fitclinic.io
```

Expected output should show the GitHub Pages IP addresses or CNAME.

### 5. Wait for DNS Propagation

- DNS propagation can take anywhere from a few minutes to 48 hours
- Most changes propagate within 1-2 hours
- You can check propagation status at: https://www.whatsmydns.net

### 6. Test Your Site

Once DNS has propagated:
1. Visit `https://artifit.fitclinic.io`
2. Verify the site loads correctly
3. Check that HTTPS is working (look for the lock icon in browser)

## Troubleshooting

### DNS Not Resolving
- Verify DNS records are entered correctly
- Wait longer for propagation
- Clear your browser cache and DNS cache:
  ```bash
  # Windows
  ipconfig /flushdns
  
  # macOS
  sudo dscacheutil -flushcache; sudo killall -HUP mDNSResponder
  
  # Linux
  sudo systemd-resolve --flush-caches
  ```

### HTTPS Not Working
- Ensure DNS is fully propagated first
- In GitHub Settings → Pages, enable "Enforce HTTPS"
- Wait a few minutes for certificate provisioning

### 404 Error
- Verify the workflow has run successfully
- Check GitHub Actions tab for deployment status
- Ensure `index.html` exists in the repository

### Custom Domain Not Saving in GitHub
- Verify the `CNAME` file exists in the repository root
- Check that it contains only: `artifit.fitclinic.io`
- Ensure no trailing whitespace or additional lines

## Provider-Specific Instructions

### Cloudflare
1. Log in to Cloudflare
2. Select your domain `fitclinic.io`
3. Go to DNS → Records
4. Add the A records or CNAME record as specified above
5. Set Proxy status to "DNS only" (gray cloud) initially
6. After DNS is working, you can enable Cloudflare proxy (orange cloud)

### GoDaddy
1. Log in to GoDaddy
2. Go to My Products → DNS
3. Select `fitclinic.io`
4. Add new records (A or CNAME)
5. Save changes

### AWS Route53
1. Open Route53 console
2. Select your hosted zone for `fitclinic.io`
3. Create record set
4. Add the A records or CNAME record
5. Create record

## Additional Resources

- [GitHub Pages Documentation](https://docs.github.com/en/pages)
- [Managing a custom domain for GitHub Pages](https://docs.github.com/en/pages/configuring-a-custom-domain-for-your-github-pages-site)
- [GitHub Pages IP Addresses](https://docs.github.com/en/pages/configuring-a-custom-domain-for-your-github-pages-site/managing-a-custom-domain-for-your-github-pages-site#configuring-an-apex-domain)

## Support

If you encounter issues:
1. Check GitHub Actions logs in the repository
2. Verify DNS configuration using dig/nslookup
3. Review GitHub Pages settings in repository
4. Ensure the CNAME file is properly formatted
