<template>
  <div class="example-component">
    <!-- Using Tailwind utility classes -->
    <div class="container mx-auto px-4 py-8">
      <h1 class="text-4xl font-bold text-center mb-8 text-gradient">
        SCSS + Tailwind CSS Example
      </h1>
      
      <!-- Using custom SCSS classes -->
      <div class="card-grid">
        <div class="custom-card">
          <h2 class="card-title">Pure SCSS Styling</h2>
          <p class="card-text">
            This card uses custom SCSS classes with variables and mixins.
          </p>
          <button class="custom-button">Learn More</button>
        </div>
        
        <div class="card glass-effect p-6 rounded-lg">
          <h2 class="text-2xl font-semibold mb-4">Tailwind Utilities</h2>
          <p class="text-gray-600 mb-4">
            This card uses Tailwind utility classes for styling.
          </p>
          <button class="btn btn-primary">Get Started</button>
        </div>
        
        <div class="hybrid-card">
          <h2 class="text-2xl font-semibold mb-4">Hybrid Approach</h2>
          <p class="text-gray-600 mb-4">
            This card combines both SCSS and Tailwind classes.
          </p>
          <button class="btn btn-success">Explore</button>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup lang="ts">
// Component logic here
</script>

<style lang="scss" scoped>
// Import variables and mixins
@import '@/assets/styles/variables';
@import '@/assets/styles/mixins';

.example-component {
  min-height: 100vh;
  background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
}

.card-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
  gap: $spacing-xl;
  margin-top: $spacing-2xl;
}

.custom-card {
  @include card($spacing-xl, $border-radius-xl);
  @include hover-lift;
  
  .card-title {
    @include heading('base');
    color: $secondary-color;
    margin-bottom: $spacing-md;
  }
  
  .card-text {
    color: $gray-600;
    line-height: $line-height-relaxed;
    margin-bottom: $spacing-lg;
  }
  
  .custom-button {
    @include button-base;
    background: $primary-color;
    color: $white;
    
    &:hover {
      background: darken($primary-color, 10%);
      transform: translateY(-2px);
    }
    
    &:active {
      transform: translateY(0);
    }
  }
}

.hybrid-card {
  // SCSS for structure
  @include card;
  @include hover-lift;
  
  // Tailwind utilities can be used in template
  // SCSS for custom styling
  background: linear-gradient(135deg, rgba(255, 255, 255, 0.9), rgba(255, 255, 255, 0.7));
  backdrop-filter: blur(10px);
  border: 1px solid rgba(255, 255, 255, 0.3);
}

// Responsive design with SCSS mixins
@include respond-to('md') {
  .card-grid {
    gap: $spacing-2xl;
  }
}

@include respond-to('lg') {
  .example-component {
    padding: $spacing-3xl 0;
  }
}
</style>
