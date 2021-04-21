<template>
  <div class="layout">
    <header class="header">
      <g-link class="home-link" to="/">
        <img src="../../static/images/logo.svg" class="logo" />
      </g-link>
      <nav class="nav">
        <g-link class="nav__link" to="/">Journal</g-link>
        <g-link class="nav__link" to="/contact/">Say Hi!</g-link>
      </nav>
    </header>
    <slot />
    <footer class="footer">
      <div class="container">
        <span>Copyright &copy; 2021</span>
      </div>
    </footer>
  </div>
</template>

<static-query>
query {
  metadata {
    siteName
  }
}
</static-query>

<style>
* {
  box-sizing: border-box;
}

body {
  --color-base: rgb(255, 255, 255);
  --color-base-1: rgb(243, 243, 243);
  --color-contrast: rgb(0, 0, 0);
  --color-contrast-1: rgb(43, 43, 43);
  font-family: -apple-system, system-ui, BlinkMacSystemFont, 'Segoe UI', Roboto,
    'Helvetica Neue', Arial, sans-serif;
  margin: 0;
  padding: 0;
  font-size: 16px;
  background: var(--color-base);
  color: var(--color-contrast);
  transition: background 0.5s ease;
}

body.dark {
  --color-base: rgb(0, 0, 0);
  --color-base-1: rgb(43, 43, 43);
  --color-contrast: rgb(255, 255, 255);
  --color-contrast-1: rgb(243, 243, 243);
}

h1 {
  letter-spacing: -0.01em;
}

.layout {
  padding: 0;
}

.layout.sticky-header {
  padding: 6rem 0 0 0;
}

.container {
  max-width: 1200px;
  margin: 0 auto;
  padding: 0 2rem;
}

@media (min-width: 860px) {
  .container,
  .header {
    padding: 0 6rem;
  }
}

a {
  color: inherit;
}

img {
  max-width: 100%;
}

.label {
  display: block;
  font-weight: 700;
  margin-bottom: 0.5rem;
}

.header {
  max-width: 1200px;
  padding: 0 2rem;
  margin: 0 auto;
  display: flex;
  justify-content: space-between;
  align-items: center;
  margin-bottom: 20px;
  height: 80px;
}

.logo {
  width: 60px;
}

.home-link {
  text-decoration: none;
}

.nav > * {
  font-size: 0.9rem;
  font-weight: 600;
  text-decoration: none;
  margin-top: 4px;
  margin-right: 3rem;
  padding-bottom: 4px;
  border-bottom: 1px solid;
  border-color: transparent;
  transition: border 0.15s;
}
.nav > *:last-of-type {
  margin: 0;
}
.nav > *:hover {
  border-color: inherit;
}
.nav > .active {
  border-color: inherit;
}
.footer {
  font-size: 0.8rem;
  padding: 6rem 0;
}
</style>
