<template>
  <div>
    
    <header class="header content">
      <div class="logo">
        <g-link to="/">Sample app</g-link>
      </div>
      <nav class="nav">
        <g-link class="nav__link" v-for="page, index in $static.pages.edges" :to="page.node.path">{{page.node.title}}</g-link>
      </nav>
    </header>
    
    <section v-if="this.$slots.hero && heroBackground" class="hero" :style="'background-image: url('+ heroBackground +');'">
      <slot name="hero"></slot>
    </section>
    <slot v-else name="hero"></slot>

    <main class="content">
      <slot></slot>
    </main>

  </div>
</template>

<static-query>
query Pages {
  pages: allWordPressPage {
    edges {
      node {
        id
        title
        path
      }
    }
  }
}
</static-query>

<script>
  export default {
    props: ['hero-background']
  }
</script>


<style>
body {
  font-family: -apple-system,system-ui,BlinkMacSystemFont,"Segoe UI",Roboto,"Helvetica Neue",Arial,sans-serif;
  margin:0;
  padding:0;
  font-size: 24px;
}

.logo a {
  color: #42b983;
  font-size: 1.5em;
  text-decoration: none;
  font-weight: bold;
}

.hero {
  width: 100%;
  height: 500px;
  background-size: cover;
  overflow: hidden;
  display: flex;
  align-items: center;
}

.hero .content {
  width: 100%;
}

.hero h1 {
  color: white;
}

.content h1 {
  padding: 0;
  margin: 0;
}

.content {
  max-width: 1200px;
  margin: 0 auto;
  padding: 40px 20px;
}

.header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  height: 80px;
  border-bottom: 1px solid #e0e0e0;
}

.nav__link {
  font-family: BlinkMacSystemFont, sans-serif;
  color: black;
  font-size: 1em;
  font-weight: bold;
  margin-left: 20px;
  text-decoration: none;
}

.nav__link.active {
  color: #42b983;
}

p, ul {
  font-size: 22px;
  font-family: "Hoefler Text", Garamond;
  line-height: 1.8;
}

h1, h2, h3, h4 {
  font-family: BlinkMacSystemFont, sans-serif;
  line-height: 1.4;
}

h1 {
  font-size: 2.5em;

}

h2 {
  font-size: 2.25em;
}

h3 {
  font-size: 1.6875em;
}

h4 {
  font-size: 1.125em;
}
</style>
