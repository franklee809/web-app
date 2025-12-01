<template>
  <div class="about">
    <h1>About Theme 2</h1>
    <p>
      This application is part of a monorepo structure that allows multiple themed applications
      to coexist while sharing common code and utilities.
    </p>
    <p>
      Each app can have its own unique design, branding, and features while leveraging shared
      components and utilities from the packages directory.
    </p>
  </div>
</template>

<style scoped lang="scss">
.about {
  max-width: 800px;
  margin: 0 auto;

  h1 {
    font-size: 2.5rem;
    background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    background-clip: text;
    margin-bottom: 2rem;
  }

  p {
    font-size: 1.1rem;
    line-height: 1.8;
    color: #666;
    margin-bottom: 1.5rem;
  }
}
</style>
