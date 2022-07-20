<template>
  <div class="container">
    <p class="quote">{{ quote }}</p>
    <p class="author">{{ author }}</p>
  </div>
</template>

<script>
export default {
  name: "",
  data() {
    return {
      quote: "quote goes here",
      author: "author name",
    };
  },
};
</script>

<style scoped lang="scss">
.container {
  background: #999;
  color: black;
  height: 100vh;
}
.quote {
}

.author {
}
</style>
