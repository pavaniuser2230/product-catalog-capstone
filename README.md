# Product Catalog Capstone

A professional-grade React + Vite product catalog demo built with client-side routing and optimized assets.

## Features
- Modular React architecture with reusable components
- React Router v6 navigation for seamless page transitions
- Product catalog with detail pages and filtering
- Responsive layout and accessible UI
- Production-ready build scripts for deployment
- TypeScript for type safety across the codebase
- Lazy-loaded images for performance

## Quick Start

### Development

1. Install dependencies:
   ```bash
   npm install
   ```

2. Start development server:
   ```bash
   npm run dev
   ```
   Open [http://localhost:4173](http://localhost:4173) in your browser.

3. Build for production:
   ```bash
   npm run build
   ```

4. Preview production build:
   ```bash
   npm run preview
   ```

## Deployment

### One-Click Deploy

Choose your platform and deploy instantly:

- **Vercel**: [![Deploy with Vercel](https://vercel.com/button)](https://vercel.com/new/clone?repository-url=https%3A%2F%2Fgithub.com%2Fyourname%2Fproduct-catalog)
- **Netlify**: [![Deploy to Netlify](https://www.netlify.com/img/deploy/button.svg)](https://app.netlify.com/start/deploy?repository=https://github.com/yourname/product-catalog)

### Manual Deployment

See [DEPLOYMENT.md](./DEPLOYMENT.md) for detailed deployment instructions for:
- Vercel (recommended)
- Netlify
- Render
- Any static hosting platform

## Project Structure

```
src/
  ├── components/      # Reusable React components
  │   └── ProductCard.tsx
  │   └── Navbar.tsx
  ├── routes/         # Page components with routing
  │   ├── Home.tsx
  │   ├── Catalog.tsx
  │   ├── ProductDetail.tsx
  │   ├── About.tsx
  │   └── NotFound.tsx
  ├── data/           # Static data and types
  │   └── products.ts
  ├── main.tsx        # React DOM entry point
  ├── App.tsx         # Root app with routing
  └── styles.css      # Global styles (4.5 KB)

public/
  └── images/         # Static image assets

dist/                 # Production build output (optimized)
```

## Architecture Highlights

### Routing (React Router v6)
- Client-side navigation for instant page transitions
- Deep linking supported (bookmark product details)
- 404 handling for missing routes

### Filtering & Search
- Real-time product filtering by category
- Search-as-you-type functionality
- Efficient memoization to prevent unnecessary re-renders

### Responsive Design
- Mobile-first CSS Grid and Flexbox
- Touch-friendly navigation and buttons
- Semantic HTML for accessibility

### Performance Optimizations
- **Lazy image loading**: `loading="lazy"` attribute on images
- **Code splitting**: Vite automatically chunks components
- **CSS minification**: ~3.8 KB final stylesheet
- **Tree shaking**: Unused code removed from bundle
- **Gzip compression**: ~57 KB gzipped (from 176 KB uncompressed)

## Build & Bundle Analysis

```
dist/index.html                0.87 kB
dist/assets/index-*.css        3.78 kB (styled components)
dist/assets/index-*.js       176.29 kB (React + routing + app code)
```

The build is optimized for production with no external dependencies beyond React and React Router.

## Available Scripts

```bash
npm run dev              # Start development server
npm run build            # Build for production
npm run preview          # Preview production build locally
npm run format           # Format code with Prettier
npm run lint             # Lint code with ESLint
```

## Technology Stack

- **React 18**: UI library
- **Vite 5**: Fast build tool and dev server
- **TypeScript 5**: Type-safe JavaScript
- **React Router 6**: Client-side routing
- **CSS 3**: Custom styling (no CSS framework needed)

## Browser Support

- Chrome/Edge (latest 2 versions)
- Firefox (latest 2 versions)
- Safari 12+
- Mobile browsers (iOS Safari 12+, Chrome Android)

## Contributing

To extend this project:

1. Add new routes in `src/routes/`
2. Create components in `src/components/`
3. Update product data in `src/data/products.ts`
4. Styles are in `src/styles.css` (global scope with BEM naming)

## License

This project is provided as an educational capstone demonstration.

## Support

For deployment questions, see [DEPLOYMENT.md](./DEPLOYMENT.md).
For technical issues, check the [troubleshooting section](./DEPLOYMENT.md#troubleshooting).
