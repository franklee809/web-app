# Web App Monorepo

This project has been restructured into a **pnpm workspace-based monorepo** containing multiple themed web applications and shared packages.

## 📚 Documentation

Please refer to [MONOREPO_GUIDE.md](MONOREPO_GUIDE.md) for detailed instructions on:
- Project structure
- Development workflow
- Adding new apps
- Working with shared packages
- Build and deployment

## 🚀 Quick Start

```bash
# Install dependencies
pnpm install

# Run all apps in development mode
pnpm dev

# Build all apps
pnpm build
```

## 📦 Apps

- **@monorepo/default**: The original application (Port 3000)
- **@monorepo/theme-2**: A new themed application variant (Port 3001)

## 🛠️ Shared Packages

- **@monorepo/shared-components**: Reusable Vue components
- **@monorepo/shared-utils**: Common utility functions
- **@monorepo/shared-types**: Shared TypeScript types
