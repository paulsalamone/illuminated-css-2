<template>
  <main>
    <NavBar />
    <Nuxt />
  </main>
</template>

<script>
export default {
  components: "ContentDoc",
};
</script>

<style>
main {
  display: grid;
  grid-template-columns: 1fr 6fr;
  width: 100%;
}
</style>
