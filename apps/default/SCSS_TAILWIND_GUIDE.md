# SCSS + Tailwind CSS Configuration Guide

This project is configured to use both **SCSS** and **Tailwind CSS** together, giving you the flexibility to use:

- Tailwind utility classes for rapid development
- SCSS variables, mixins, and nested styles for custom components
- A hybrid approach combining both

## 📁 Project Structure

```
src/
├── assets/
│   ├── main.scss              # Main stylesheet (imports Tailwind + SCSS)
│   └── styles/
│       ├── _variables.scss    # SCSS variables (colors, spacing, typography, etc.)
│       └── _mixins.scss       # Reusable SCSS mixins
└── components/
    └── ExampleComponent.vue   # Example showing SCSS + Tailwind usage
```

## 🎨 Using SCSS Variables

SCSS variables are defined in `src/assets/styles/_variables.scss`:

```scss
// In your component
<style lang="scss" scoped>
@import '@/assets/styles/variables';

.my-element {
  color: $primary-color;
  padding: $spacing-lg;
  border-radius: $border-radius-md;
  box-shadow: $shadow-lg;
}
</style>
```

### Available Variables

- **Colors**: `$primary-color`, `$secondary-color`, `$gray-100` to `$gray-900`, etc.
- **Spacing**: `$spacing-xs` (4px) to `$spacing-3xl` (64px)
- **Typography**: `$font-size-xs` to `$font-size-4xl`, `$font-weight-light` to `$font-weight-bold`
- **Border Radius**: `$border-radius-sm` to `$border-radius-2xl`
- **Shadows**: `$shadow-sm` to `$shadow-2xl`
- **Transitions**: `$transition-fast`, `$transition-base`, `$transition-slow`

## 🔧 Using SCSS Mixins

Mixins are defined in `src/assets/styles/_mixins.scss`:

```scss
<style lang="scss" scoped>
@import '@/assets/styles/mixins';

.my-card {
  @include card;           // Applies card styling
  @include hover-lift;     // Adds lift effect on hover
}

.centered-content {
  @include flex-center;    // Centers content with flexbox
}

.my-heading {
  @include heading('lg');  // Applies heading styles
}

// Responsive design
@include respond-to('md') {
  .my-element {
    font-size: 1.5rem;
  }
}
</style>
```

### Available Mixins

- **Layout**: `flex-center`, `flex-between`, `flex-column`, `absolute-center`, `absolute-cover`
- **Typography**: `heading($size)`, `truncate`, `line-clamp($lines)`
- **Components**: `card($padding, $radius)`, `button-base`
- **Effects**: `hover-lift`, `gradient-bg($start, $end, $direction)`, `focus-ring($color)`
- **Responsive**: `respond-to($breakpoint)` - breakpoints: 'sm', 'md', 'lg', 'xl', '2xl'
- **Utilities**: `transition($properties...)`, `custom-scrollbar($width, $track, $thumb)`

## 🎯 Using Tailwind CSS

Tailwind utility classes work as normal in your templates:

```vue
<template>
  <div class="flex items-center justify-center p-4 bg-blue-500 text-white rounded-lg shadow-md">
    <h1 class="text-2xl font-bold">Hello Tailwind!</h1>
  </div>
</template>
```

### Custom Tailwind Components

Custom component classes are defined in `main.scss`:

```vue
<template>
  <!-- Button variants -->
  <button class="btn btn-primary">Primary Button</button>
  <button class="btn btn-secondary">Secondary Button</button>
  <button class="btn btn-success">Success Button</button>
  <button class="btn btn-danger">Danger Button</button>
  <button class="btn btn-outline">Outline Button</button>

  <!-- Card with hover effect -->
  <div class="card">Card content</div>

  <!-- Custom container -->
  <div class="container-custom">Responsive container</div>
</template>
```

### Custom Tailwind Utilities

```vue
<template>
  <!-- Flex utilities -->
  <div class="flex-center">Centered content</div>
  <div class="flex-between">Space between content</div>

  <!-- Text gradient -->
  <h1 class="text-gradient">Gradient text</h1>

  <!-- Glass effect -->
  <div class="glass-effect p-6">Glassmorphism effect</div>
</template>
```

## 🔄 Hybrid Approach (Recommended)

Combine both for maximum flexibility:

```vue
<template>
  <div class="custom-component">
    <!-- Tailwind for utilities, SCSS for custom styles -->
    <div class="flex items-center gap-4 p-6">
      <h2 class="text-2xl font-bold">Title</h2>
      <button class="custom-button">Click me</button>
    </div>
  </div>
</template>

<style lang="scss" scoped>
@import '@/assets/styles/variables';
@import '@/assets/styles/mixins';

.custom-component {
  @include card;
  background: $white;

  .custom-button {
    @include button-base;
    background: $primary-color;
    color: $white;

    &:hover {
      background: darken($primary-color, 10%);
    }
  }
}
</style>
```

## 📝 Component Style Patterns

### Pattern 1: Pure Tailwind

```vue
<template>
  <div class="bg-white rounded-lg shadow-md p-6 hover:shadow-lg transition-shadow">
    <h2 class="text-2xl font-bold mb-4">Title</h2>
    <p class="text-gray-600">Content</p>
  </div>
</template>
```

### Pattern 2: Pure SCSS

```vue
<template>
  <div class="my-card">
    <h2 class="title">Title</h2>
    <p class="content">Content</p>
  </div>
</template>

<style lang="scss" scoped>
@import '@/assets/styles/variables';
@import '@/assets/styles/mixins';

.my-card {
  @include card;
  @include hover-lift;

  .title {
    @include heading('base');
    margin-bottom: $spacing-md;
  }

  .content {
    color: $gray-600;
  }
}
</style>
```

### Pattern 3: Hybrid (Best of Both)

```vue
<template>
  <div class="my-card">
    <!-- Tailwind for layout and spacing -->
    <div class="flex items-center justify-between mb-4">
      <h2 class="text-2xl font-bold">Title</h2>
      <button class="custom-btn">Action</button>
    </div>
    <p class="text-gray-600">Content</p>
  </div>
</template>

<style lang="scss" scoped>
@import '@/assets/styles/variables';
@import '@/assets/styles/mixins';

.my-card {
  // SCSS for complex custom styling
  @include card;
  @include hover-lift;
  background: linear-gradient(135deg, $white, $gray-100);
}

.custom-btn {
  @include button-base;
  background: $primary-color;
  color: $white;

  &:hover {
    background: darken($primary-color, 10%);
  }
}
</style>
```

## 🚀 Development

```bash
# Install dependencies
npm install

# Start development server
npm run dev

# Build for production
npm run build
```

## 📚 Configuration Files

- **`tailwind.config.js`**: Tailwind CSS configuration
- **`postcss.config.js`**: PostCSS configuration (includes Tailwind processing)
- **`vite.config.ts`**: Vite configuration (handles SCSS compilation)
- **`src/assets/main.scss`**: Main stylesheet entry point

## 💡 Best Practices

1. **Use Tailwind for**: Layout, spacing, responsive design, common utilities
2. **Use SCSS for**: Complex custom components, theme variables, reusable patterns
3. **Use Mixins for**: Repeated style patterns, responsive breakpoints, complex effects
4. **Use Variables for**: Consistent design tokens (colors, spacing, typography)

## 🎨 Customization

### Adding New Colors

Edit `src/assets/styles/_variables.scss`:

```scss
$brand-color: #ff6b6b;
$accent-color: #4ecdc4;
```

### Adding New Mixins

Edit `src/assets/styles/_mixins.scss`:

```scss
@mixin my-custom-mixin {
  // Your styles here
}
```

### Extending Tailwind

Edit `tailwind.config.js`:

```js
export default {
  theme: {
    extend: {
      colors: {
        brand: '#ff6b6b'
      }
    }
  }
}
```

## 🔍 Troubleshooting

### SCSS imports not working

Make sure you're using the `@` alias:

```scss
@import '@/assets/styles/variables';
```

### Tailwind classes not applying

1. Check that your file is included in `tailwind.config.js` content array
2. Ensure `main.scss` is imported in `main.ts`
3. Restart the dev server

### Style conflicts

- Tailwind utilities have high specificity
- Use `!important` sparingly in SCSS
- Leverage Tailwind's `@layer` directive for custom utilities

## 📖 Resources

- [Tailwind CSS Documentation](https://tailwindcss.com/docs)
- [SCSS Documentation](https://sass-lang.com/documentation)
- [Vite CSS Documentation](https://vitejs.dev/guide/features.html#css)
