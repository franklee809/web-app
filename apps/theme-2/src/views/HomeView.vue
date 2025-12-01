<template>
  <div class="home">
    <h1>Welcome to Theme 2</h1>
    <p class="description">
      This is a second themed application in the monorepo. It demonstrates how multiple apps
      can share common packages while maintaining their own unique styling and branding.
    </p>
    
    <div class="features">
      <div class="feature-card">
        <h3>🎨 Unique Theme</h3>
        <p>Purple gradient design with custom styling</p>
      </div>
      <div class="feature-card">
        <h3>📦 Shared Packages</h3>
        <p>Uses common utilities and components</p>
      </div>
      <div class="feature-card">
        <h3>🚀 Independent Build</h3>
        <p>Can be built and deployed separately</p>
      </div>
    </div>
  </div>
</template>

<style scoped lang="scss">
.home {
  max-width: 1200px;
  margin: 0 auto;

  h1 {
    font-size: 3rem;
    background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    background-clip: text;
    margin-bottom: 1rem;
  }

  .description {
    font-size: 1.2rem;
    color: #666;
    margin-bottom: 3rem;
    line-height: 1.6;
  }

  .features {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
    gap: 2rem;

    .feature-card {
      padding: 2rem;
      border-radius: 1rem;
      background: linear-gradient(135deg, rgba(102, 126, 234, 0.1) 0%, rgba(118, 75, 162, 0.1) 100%);
      border: 2px solid rgba(102, 126, 234, 0.2);
      transition: transform 0.3s, box-shadow 0.3s;

      &:hover {
        transform: translateY(-5px);
        box-shadow: 0 10px 30px rgba(102, 126, 234, 0.2);
      }

      h3 {
        font-size: 1.5rem;
        margin-bottom: 0.5rem;
        color: #667eea;
      }

      p {
        color: #666;
        line-height: 1.5;
      }
    }
  }
}
</style>
