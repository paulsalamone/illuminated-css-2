<template>
  <div>
    <nav>
      <nuxt-link to="/"> <h1>illuminated css</h1></nuxt-link>
      <nuxt-link to="/q001-cubicles">001 cubicles</nuxt-link>
      <nuxt-link to="/q002-coffee">002 coffee</nuxt-link>
      <nuxt-link to="/q003-diamonds">003 diamonds</nuxt-link>
      <nuxt-link to="/q004-cd">004 CDs</nuxt-link>
      <nuxt-link to="/q005-globe">004 Globe</nuxt-link>
    </nav>
  </div>
</template>

<script>
export default {
  name: "IndexPage",
};
</script>

<style scoped>
nav {
  background: black;
  color: white;
  display: flex;
  flex-direction: column;
}

nav a {
  background: black;
  color: white;
  text-decoration: none;
}

nuxt-link {
  color: white;
}
</style>
