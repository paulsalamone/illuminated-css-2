<template>
  <div class="container">
    <div class="globe"></div>

    <!-- make the letters grow larger then smaller as sentence progresses -->

    <div class="quote">
      <p>
        <span
          v-for="(letter, index) in sizedLetters"
          :key="index"
          :style="{
            fontSize: `${fontSizes[index] + 20}px`,
          }"
        >
          {{ letter }}
        </span>
      </p>
      <p>-Dave Attell</p>
    </div>
  </div>
</template>

<script>
export default {
  name: "",
  data() {
    return {
      quote:
        "So, I travel a lot. I hate traveling, mostly cause my dad used to beat me with a globe.",
    };
  },
  computed: {
    sizedLetters() {
      return this.quote.split(" ");
    },
    // fontSizes() {
    //   let results = [];
    //   for (let i = 0; i < this.sizedLetters.length; i++) {
    //     results.push(Math.floor(Math.random() * 50));
    //   }
    //   console.log(results);
    //   return results;
    // },
    fontSizes() {
      let results = [];
      for (let i = 0; i < this.sizedLetters.length; i++) {
        i < this.sizedLetters.length / 2
          ? results.push(i * 10)
          : results.push(130 - i * 7);
      }
      console.log(results);
      return results;
    },
  },
};
</script>

<style scoped lang="scss">
.globe {
  background: linear-gradient(navy 20%, orange);
  border-radius: 50%;
  width: 200px;
  height: 200px;
}

.container {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  text-align: center;
  background: linear-gradient(navy 85%, orange);
  height: 100vh;
  padding: 40px;
  box-sizing: border-box;
}

.quote {
  color: orange;
  font-family: Cambria, Cochin, Georgia, Times, "Times New Roman", serif;
  transform: translateY(80px);

  p:nth-child(1) {
    font-size: 3rem;
    line-height: 40px;
    z-index: 10;
    position: relative;
  }

  p:nth-child(2) {
    font-size: 3rem;
    margin-top: 20px;
    color: navy;
    text-shadow: 0 0 10px orange, 0 0 5px orange;
  }
}
</style>
