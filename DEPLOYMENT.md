# Product Catalog Capstone — Deployment Guide

This guide provides step-by-step instructions for deploying the Capstone project to production platforms.

## Prerequisites

- Node.js 18+ installed locally
- Git repository initialized (optional but recommended)
- Account on your chosen hosting platform
- CLI tools installed (as needed per platform)

## Local Verification

Before deploying, test the build and preview:

```bash
# Install dependencies
npm install

# Run development server (local testing)
npm run dev

# Build for production
npm run build

# Preview production build locally
npm run preview
```

The dev server runs on `http://localhost:4173` by default.

---

## Deployment Options

### 1. Vercel (Recommended for Vite + React)

Vercel offers optimal performance for React applications with minimal configuration.

**Steps:**

1. **Create Vercel account**
   - Go to [vercel.com](https://vercel.com)
   - Sign up using GitHub, GitLab, or email

2. **Push code to Git repository**
   ```bash
   git init
   git add .
   git commit -m "Initial commit: Product Catalog Capstone"
   git push origin main
   ```

3. **Deploy from Vercel dashboard**
   - Click "Add New Project"
   - Select your Git repository
   - Framework: Select "Vite"
   - Build command: `npm run build`
   - Output directory: `dist`
   - Click "Deploy"

4. **Alternative: Deploy via Vercel CLI**
   ```bash
   npm install -g vercel
   vercel deploy --prod
   ```

**Result:** Your app receives a public URL and automatic HTTPS.

---

### 2. Netlify

Netlify provides edge computing and serverless functions alongside static hosting.

**Steps:**

1. **Create Netlify account**
   - Go to [netlify.com](https://netlify.com)
   - Sign up using GitHub, GitLab, GitBucket, or email

2. **Deploy via Netlify CLI (quickest method)**
   ```bash
   npm install -g netlify-cli
   netlify deploy --prod
   ```

3. **Or deploy from Git**
   - Connect your Git repository in Netlify dashboard
   - Select your project
   - Netlify auto-detects `netlify.toml` configuration
   - Your site deploys on every push to main

**Result:** Automatic deployments, preview links, and rollback capability.

---

### 3. Render

Render offers a modern alternative with built-in CI/CD and zero cold starts (paid tier).

**Steps:**

1. **Create Render account**
   - Go to [render.com](https://render.com)
   - Sign up using GitHub or email

2. **Create new Static Site**
   - Click "New +" → "Static Site"
   - Connect your Git repository
   - Set publish directory: `dist`
   - Build command: `npm run build`
   - Click "Create Static Site"

3. **Render automatically deploys on git push**

**Result:** Your app is live with a render.com subdomain and custom domain support.

---

## Production Optimization Checklist

- ✅ **TypeScript compilation** — All `.ts` and `.tsx` files are type-checked
- ✅ **CSS optimization** — Styles minified and inlined
- ✅ **JavaScript minification** — Vite tree-shakes unused code
- ✅ **Asset optimization** — Images use lazy loading (`loading="lazy"`)
- ✅ **Build size** — ~176KB (gzipped: ~57KB) per bundle analysis
- ✅ **SEO-ready** — Meta tags, semantic HTML, and accessible navigation
- ✅ **Responsive design** — Mobile, tablet, and desktop support

## Environment Variables

If you need environment variables (e.g., API endpoints):

1. Create `.env.local` in the project root (not committed to Git):
   ```
   VITE_API_URL=https://api.example.com
   ```

2. Reference in code:
   ```typescript
   const apiUrl = import.meta.env.VITE_API_URL;
   ```

3. Add corresponding variables in platform dashboard:
   - **Vercel**: Project Settings → Environment Variables
   - **Netlify**: Site Settings → Build & Deploy → Environment
   - **Render**: Environment → Environment Variables

## Monitoring & Analytics

### Performance
- Use Vercel Analytics, Netlify Analytics, or Google Analytics
- Monitor Core Web Vitals and loading time

### Error Tracking
- Integrate Sentry or LogRocket for error reporting
- Track user interactions and performance bottlenecks

## Domain Setup

### Custom Domain on Vercel
```
1. Go to Project Settings → Domains
2. Add your domain (or subdomain)
3. Update DNS records as directed
```

### Custom Domain on Netlify
```
1. Site Settings → Domain Management
2. Add custom domain
3. DNS will auto-configure if using Netlify DNS
```

### Custom Domain on Render
```
1. Dashboard → Environment → Custom Domain
2. Point your DNS to the provided Render nameservers
```

## Continuous Deployment

All three platforms support automatic deployments on Git push. Simply push to your main branch:

```bash
git add .
git commit -m "Feature: Add product filters"
git push origin main
```

Your app updates instantly on the live URL.

## Rollback & Versioning

- **Vercel & Netlify**: Automatic deployment history; click to rollback
- **Render**: Automatic deployments; redeploy from git history

## Troubleshooting

**Issue: Build fails during deployment**
- Check that all dependencies are in `package.json`
- Verify TypeScript has no errors: `npm run build` locally
- Check build logs on platform dashboard

**Issue: Site shows blank page**
- Check browser console for errors
- Verify `dist/` folder contains `index.html`
- Confirm server is serving SPA correctly (all routes → `index.html`)

**Issue: Assets not loading**
- Confirm all images in `public/` or imported in code
- Check relative vs. absolute paths (use absolute: `/image.png`)
- Verify base path if deploying to subdirectory

## Next Steps

1. Test the live deployment
2. Set up custom domain
3. Configure analytics and error tracking
4. Set up CI/CD pipelines if needed
5. Monitor performance metrics

---

**Deployment complete!** Your Product Catalog Capstone is now live and production-ready.
