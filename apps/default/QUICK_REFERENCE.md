# SCSS + Tailwind Quick Reference

## 🎯 Quick Start Template

```vue
<template>
  <div class="my-component">
    <!-- Mix Tailwind utilities with custom classes -->
    <div class="flex items-center gap-4 p-6">
      <h1 class="text-2xl font-bold">Hello World</h1>
    </div>
  </div>
</template>

<script setup lang="ts">
// Component logic
</script>

<style lang="scss" scoped>
@import '@/assets/styles/variables';
@import '@/assets/styles/mixins';

.my-component {
  @include card;
  background: $white;
}
</style>
```

## 📦 Common SCSS Variables

```scss
// Colors
$primary-color: #42b983;
$secondary-color: #2c3e50;
$gray-100 to $gray-900

// Spacing
$spacing-xs: 4px
$spacing-sm: 8px
$spacing-md: 16px
$spacing-lg: 24px
$spacing-xl: 32px
$spacing-2xl: 48px
$spacing-3xl: 64px

// Typography
$font-size-xs: 12px
$font-size-sm: 14px
$font-size-base: 16px
$font-size-lg: 18px
$font-size-xl: 20px
$font-size-2xl: 24px
$font-size-3xl: 30px
$font-size-4xl: 36px

// Border Radius
$border-radius-sm: 4px
$border-radius-md: 8px
$border-radius-lg: 12px
$border-radius-xl: 16px
$border-radius-2xl: 24px

// Shadows
$shadow-sm, $shadow-md, $shadow-lg, $shadow-xl, $shadow-2xl
```

## 🔧 Common SCSS Mixins

```scss
// Layout
@include flex-center; // Centers content
@include flex-between; // Space between
@include flex-column; // Flex column

// Components
@include card; // Card styling
@include card($spacing-xl, $border-radius-xl); // Custom card
@include button-base; // Button base styles

// Effects
@include hover-lift; // Lift on hover
@include gradient-bg($start, $end, $direction);
@include transition(transform, opacity);

// Typography
@include heading('sm'); // Small heading
@include heading('base'); // Base heading
@include heading('lg'); // Large heading
@include heading('xl'); // XL heading
@include truncate; // Truncate text
@include line-clamp(3); // Clamp to 3 lines

// Responsive
@include respond-to('sm') {
} // 640px+
@include respond-to('md') {
} // 768px+
@include respond-to('lg') {
} // 1024px+
@include respond-to('xl') {
} // 1280px+
@include respond-to('2xl') {
} // 1536px+
```

## 🎨 Custom Tailwind Classes

```html
<!-- Buttons -->
<button class="btn btn-primary">Primary</button>
<button class="btn btn-secondary">Secondary</button>
<button class="btn btn-success">Success</button>
<button class="btn btn-danger">Danger</button>
<button class="btn btn-outline">Outline</button>

<!-- Card -->
<div class="card">Card with hover lift</div>

<!-- Container -->
<div class="container-custom">Responsive container</div>

<!-- Utilities -->
<div class="flex-center">Centered</div>
<div class="flex-between">Space between</div>
<h1 class="text-gradient">Gradient text</h1>
<div class="glass-effect">Glass effect</div>
```

## 💡 Usage Patterns

### Pattern 1: Tailwind-First

```vue
<div class="bg-white rounded-lg shadow-md p-6 hover:shadow-lg">
  <h2 class="text-2xl font-bold mb-4">Title</h2>
</div>
```

### Pattern 2: SCSS-First

```vue
<div class="custom-card">
  <h2 class="title">Title</h2>
</div>

<style lang="scss" scoped>
@import '@/assets/styles/variables';
@import '@/assets/styles/mixins';

.custom-card {
  @include card;
  @include hover-lift;
}
</style>
```

### Pattern 3: Hybrid

```vue
<div class="custom-card">
  <div class="flex items-center gap-4">
    <h2 class="text-2xl font-bold">Title</h2>
  </div>
</div>

<style lang="scss" scoped>
.custom-card {
  @include card;
  background: linear-gradient(135deg, $white, $gray-100);
}
</style>
```

## 🎯 When to Use What

**Use Tailwind for:**

- ✅ Layout (flex, grid)
- ✅ Spacing (p-4, m-6, gap-2)
- ✅ Typography (text-xl, font-bold)
- ✅ Colors (bg-blue-500, text-gray-600)
- ✅ Responsive design (md:flex, lg:grid)
- ✅ Quick prototyping

**Use SCSS for:**

- ✅ Complex custom components
- ✅ Reusable style patterns
- ✅ Theme variables
- ✅ Nested selectors
- ✅ Advanced hover/active states
- ✅ Custom animations

## 🚀 Commands

```bash
npm run dev      # Start dev server
npm run build    # Build for production
npm run preview  # Preview production build
```

## 📁 File Structure

```
src/
├── assets/
│   ├── main.scss              # Main entry (imports Tailwind + SCSS)
│   └── styles/
│       ├── _variables.scss    # Design tokens
│       └── _mixins.scss       # Reusable mixins
└── components/
    └── *.vue                  # Your components
```

## 🔥 Pro Tips

1. **Import once per component**: Always import variables and mixins in scoped styles
2. **Use @apply sparingly**: Prefer SCSS mixins for complex patterns
3. **Combine strengths**: Tailwind for layout, SCSS for custom styling
4. **Consistent naming**: Use kebab-case for classes, $variables for SCSS
5. **Responsive first**: Use Tailwind's responsive utilities, then SCSS mixins
