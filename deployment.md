# 🚀 Deployment Guide - Coastal Fitness & Correction

## Quick Start (Vercel - Recommended)

1. **Install Vercel CLI**
   ```bash
   npm install -g vercel
   ```

2. **Deploy**
   ```bash
   vercel --prod
   ```

3. **Follow prompts**
   - Set up and deploy: `Y`
   - Which scope: Select your account
   - Link to existing project: `N`
   - Project name: `coastal-fitness`
   - Directory: `./`
   - Override settings: `N`

Your app will be live at: `https://coastal-fitness.vercel.app`

## GitHub Pages Deployment

1. **Create Repository**
   ```bash
   git init
   git add .
   git commit -m "Initial commit"
   git remote add origin https://github.com/yourusername/coastal-fitness.git
   git push -u origin main
   ```

2. **Enable GitHub Pages**
   - Go to repository Settings
   - Click "Pages" in sidebar
   - Source: Deploy from branch
   - Branch: main
   - Folder: / (root)
   - Click Save

3. **Access Your App**
   - URL: `https://yourusername.github.io/coastal-fitness`
   - May take 5-10 minutes to deploy

## Netlify Deployment

1. **Drag & Drop Method**
   - Visit [netlify.com](https://netlify.com)
   - Drag your project folder to the deployment area
   - Done!

2. **CLI Method**
   ```bash
   npm install -g netlify-cli
   netlify deploy --prod
   ```

## Custom Domain Setup

### Vercel
```bash
vercel domains add yourdomain.com
```

### GitHub Pages
1. Add `CNAME` file with your domain
2. Configure DNS:
   - A Record: `185.199.108.153`
   - A Record: `185.199.109.153`
   - A Record: `185.199.110.153`
   - A Record: `185.199.111.153`

### Netlify
1. Domain Settings → Add custom domain
2. Follow DNS configuration instructions

## Environment Configuration

No environment variables needed! Everything runs in the browser.

## Performance Optimization

1. **Enable Compression**
   - Already configured in `vercel.json`
   - GitHub Pages: Automatic
   - Netlify: Automatic

2. **Cache Headers**
   - Configured in `vercel.json`
   - Improves load times

## Monitoring

1. **Vercel Analytics**
   ```bash
   vercel analytics enable
   ```

2. **Google Analytics** (Optional)
   Add before `</head>` in index.html:
   ```html
   <script async src="https://www.googletagmanager.com/gtag/js?id=GA_MEASUREMENT_ID"></script>
   <script>
     window.dataLayer = window.dataLayer || [];
     function gtag(){dataLayer.push(arguments);}
     gtag('js', new Date());
     gtag('config', 'GA_MEASUREMENT_ID');
   </script>
   ```

## Backup Strategy

1. **Automated Exports**
   - Login as Engineer weekly
   - Export all data to .txt
   - Store in secure location

2. **Version Control**
   ```bash
   git add .
   git commit -m "Weekly backup"
   git push
   ```

## Troubleshooting

### Blank Page
- Check browser console for errors
- Clear browser cache
- Try incognito mode

### Data Not Saving
- Check localStorage quota (5-10MB limit)
- Export and reset if needed
- Use Engineer role for maintenance

### Slow Performance
- Clear old data via Engineer dashboard
- Limit to 200 active clients
- Use modern browser

## SSL Certificate

- Vercel: Automatic
- GitHub Pages: Automatic with custom domain
- Netlify: Automatic

## Update Process

1. Make changes to `index.html`
2. Test locally
3. Commit to git
4. Deploy:
   - Vercel: `vercel --prod`
   - GitHub: `git push`
   - Netlify: Drag & drop

## Rollback

### Vercel
```bash
vercel rollback
```

### GitHub Pages
```bash
git revert HEAD
git push
```

## Support

Issues? Contact: josh.lerner@coastal.com

---
*Last updated: 2024*