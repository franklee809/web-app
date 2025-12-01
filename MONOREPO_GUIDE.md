# Monorepo Guide

This project is structured as a **pnpm workspace-based monorepo** that supports multiple themed web applications with shared packages.

## 📁 Project Structure

```
web-app/
├── apps/                      # Application workspaces
│   ├── default/              # Default themed app (port 3000)
│   │   ├── src/
│   │   ├── public/
│   │   ├── index.html
│   │   ├── package.json
│   │   └── vite.config.ts
│   └── theme-2/              # Second themed app (port 3001)
│       ├── src/
│       ├── public/
│       ├── index.html
│       ├── package.json
│       └── vite.config.ts
├── packages/                  # Shared packages
│   ├── shared-components/    # Shared Vue components
│   ├── shared-utils/         # Shared utilities
│   └── shared-types/         # Shared TypeScript types
├── pnpm-workspace.yaml       # pnpm workspace configuration
└── package.json              # Root package.json with scripts
```

## 🚀 Getting Started

### Prerequisites

- Node.js 20+
- pnpm (installed globally)

### Installation

```bash
# Install pnpm globally if not already installed
npm install -g pnpm

# Install all dependencies
pnpm install
```

## 📜 Available Scripts

### Development

```bash
# Run all apps in development mode (parallel)
pnpm dev

# Run specific app
pnpm dev:default    # Runs on http://localhost:3000
pnpm dev:theme-2    # Runs on http://localhost:3001
```

### Build

```bash
# Build all apps
pnpm build

# Build specific app
pnpm build:default
pnpm build:theme-2
```

### Preview

```bash
# Preview all built apps
pnpm preview

# Preview specific app
pnpm preview:default
pnpm preview:theme-2
```

### Testing & Linting

```bash
# Run tests for all apps
pnpm test

# Run tests for specific app
pnpm test:default

# Lint all apps
pnpm lint

# Format all apps
pnpm format

# Type check all workspaces
pnpm type-check
```

### Maintenance

```bash
# Clean all node_modules and dist folders
pnpm clean
```

## 🎨 Adding a New Themed App

1. **Create app directory**:
   ```bash
   mkdir -p apps/my-new-app/src
   ```

2. **Copy structure from existing app**:
   ```bash
   cp -r apps/default/* apps/my-new-app/
   ```

3. **Update `apps/my-new-app/package.json`**:
   ```json
   {
     "name": "@monorepo/my-new-app",
     "dependencies": {
       "@monorepo/shared-components": "workspace:*",
       "@monorepo/shared-utils": "workspace:*",
       "@monorepo/shared-types": "workspace:*"
     }
   }
   ```

4. **Update `apps/my-new-app/vite.config.ts`**:
   ```typescript
   server: {
     port: 3002,  // Use unique port
     strictPort: true
   }
   ```

5. **Add scripts to root `package.json`**:
   ```json
   {
     "scripts": {
       "dev:my-new-app": "pnpm --filter @monorepo/my-new-app dev",
       "build:my-new-app": "pnpm --filter @monorepo/my-new-app build"
     }
   }
   ```

6. **Install dependencies**:
   ```bash
   pnpm install
   ```

7. **Customize your theme** in the app's components and styles!

## 📦 Working with Shared Packages

### Using Shared Packages in Apps

```typescript
// In any app's component or file
import { formatDate } from '@monorepo/shared-utils'
import type { AppConfig } from '@monorepo/shared-types'
// import { Button } from '@monorepo/shared-components'

const config: AppConfig = {
  name: 'My App',
  version: '1.0.0',
  theme: 'dark'
}
```

### Adding to Shared Packages

#### Shared Components (`packages/shared-components`)

1. Create your component:
   ```bash
   # Create component file
   touch packages/shared-components/src/components/Button.vue
   ```

2. Export it in `packages/shared-components/src/index.ts`:
   ```typescript
   export { default as Button } from './components/Button.vue'
   ```

#### Shared Utils (`packages/shared-utils`)

1. Add utility function in `packages/shared-utils/src/index.ts`:
   ```typescript
   export const myUtil = () => {
     // utility logic
   }
   ```

#### Shared Types (`packages/shared-types`)

1. Add types in `packages/shared-types/src/index.ts`:
   ```typescript
   export interface MyType {
     id: string
     name: string
   }
   ```

## 🔧 How It Works

### pnpm Workspaces

The `pnpm-workspace.yaml` file defines which directories are workspaces:

```yaml
packages:
  - 'apps/*'
  - 'packages/*'
```

### Workspace Dependencies

Apps can depend on shared packages using the `workspace:*` protocol:

```json
{
  "dependencies": {
    "@monorepo/shared-utils": "workspace:*"
  }
}
```

This creates a symlink to the local package, enabling:
- ✅ Instant updates when shared code changes
- ✅ No need to rebuild shared packages
- ✅ Type-safe imports with TypeScript
- ✅ Hot module replacement in development

### Port Configuration

Each app runs on a unique port:
- `apps/default`: Port 3000
- `apps/theme-2`: Port 3001
- Future apps: Port 3002, 3003, etc.

## 🎯 Micro-Frontend Architecture

This monorepo supports a micro-frontend approach where:

1. **Independent Deployment**: Each app can be built and deployed separately
2. **Shared Code**: Common logic lives in `packages/`
3. **Unique Themes**: Each app has its own styling and branding
4. **Independent Development**: Teams can work on different apps simultaneously

## 🐛 Troubleshooting

### Issue: "Cannot find module '@monorepo/...'"

**Solution**: Run `pnpm install` to ensure workspace links are created.

### Issue: Changes to shared packages not reflecting

**Solution**: 
1. Restart the dev server
2. Clear Vite cache: `rm -rf apps/*/node_modules/.vite`

### Issue: Port already in use

**Solution**: 
1. Change the port in the app's `vite.config.ts`
2. Or kill the process using the port: `lsof -ti:3000 | xargs kill`

### Issue: TypeScript errors in shared packages

**Solution**: Run `pnpm type-check` to see all type errors across workspaces.

## 📚 Learn More

- [pnpm Workspaces Documentation](https://pnpm.io/workspaces)
- [Vite Documentation](https://vitejs.dev/)
- [Vue 3 Documentation](https://vuejs.org/)
- [Micro-Frontends](https://micro-frontends.org/)

## 🤝 Contributing

1. Create a new branch for your feature
2. Make changes in the appropriate app or shared package
3. Test your changes: `pnpm test`
4. Lint your code: `pnpm lint`
5. Build to ensure no errors: `pnpm build`
6. Submit a pull request

---

**Happy coding! 🚀**
