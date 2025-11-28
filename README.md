# The Port - Curiosity Marketplace

**The Port** is a Shopify Hydrogen storefront for curiosity-related merchandise, powered by Shopify's headless commerce stack and deployed on Oxygen.

## Tech Stack

- **Framework**: [Hydrogen](https://shopify.dev/custom-storefronts/hydrogen) (React + Remix)
- **Hosting**: [Oxygen](https://shopify.dev/custom-storefronts/oxygen) (Shopify's edge hosting)
- **Styling**: Tailwind CSS
- **Language**: TypeScript

## Quick Start

### Prerequisites

- Node.js 20+
- npm 8.19+
- A Shopify store on Basic plan or higher
- Hydrogen sales channel installed in Shopify Admin

### 1. Install Dependencies

```bash
npm install
```

### 2. Connect to Your Shopify Store

```bash
# Authenticate with Shopify (opens browser)
shopify auth login

# Link this project to your store
npx shopify hydrogen link

# Pull environment variables
npx shopify hydrogen env pull
```

### 3. Run Development Server

```bash
npm run dev
```

Visit http://localhost:3000 to see your storefront.

## Deployment

### Manual Deploy to Oxygen

```bash
npx shopify hydrogen deploy
```

Choose "Preview" for testing, or "Production" for the live site.

### CI/CD with GitHub

1. Go to Shopify Admin → Sales channels → Hydrogen
2. Open your storefront
3. Click "Connect repository"
4. Connect to `sunnypatneedi/the-port`
5. Map branches:
   - `main` → Production
   - `dev` → Preview

Now pushes auto-deploy:
- Push to `dev` → Preview environment
- Merge to `main` → Production

## Project Structure

```
the-port/
├── app/
│   ├── components/     # Reusable UI components
│   ├── data/           # Data fetching utilities
│   ├── graphql/        # GraphQL queries/mutations
│   ├── hooks/          # Custom React hooks
│   ├── lib/            # Utility functions
│   ├── routes/         # Page routes (Remix file-based routing)
│   ├── styles/         # CSS and fonts
│   └── root.tsx        # Root layout
├── public/             # Static assets
├── server.ts           # Server entry point
└── vite.config.ts      # Vite configuration
```

## Key Routes

| Route | Description |
|-------|-------------|
| `/` | Home page |
| `/products` | All products |
| `/products/:handle` | Product detail |
| `/collections` | All collections |
| `/collections/:handle` | Collection page |
| `/cart` | Shopping cart |
| `/account` | Customer account |
| `/search` | Search results |

## Scripts

```bash
npm run dev        # Start dev server
npm run build      # Production build
npm run preview    # Preview production build
npm run typecheck  # Run TypeScript checks
npm run lint       # Run ESLint
npm run format     # Format with Prettier
```

## Environment Variables

Create a `.env` file (or run `npx shopify hydrogen env pull`):

```env
PUBLIC_STORE_DOMAIN=your-store.myshopify.com
PUBLIC_STOREFRONT_API_TOKEN=your-token
SESSION_SECRET=your-secret
```

## Customization

### Branding

- **Colors**: Edit `tailwind.config.js`
- **Fonts**: Update `app/styles/custom-font.css`
- **Logo**: Replace assets in `app/assets/`

### Components

Key components to customize:
- `app/components/Hero.tsx` - Home hero section
- `app/components/PageLayout.tsx` - Global header/footer
- `app/components/ProductCard.tsx` - Product display

## Resources

- [Hydrogen Docs](https://shopify.dev/custom-storefronts/hydrogen)
- [Remix Docs](https://remix.run/docs)
- [Tailwind CSS](https://tailwindcss.com/docs)
- [Shopify Storefront API](https://shopify.dev/api/storefront)
