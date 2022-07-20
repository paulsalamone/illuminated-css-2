<template>
  <div class="container">
    <div class="box">
      <div class="zigzag">
        <div v-for="(zig, index) in zigzagsLong" :key="index" class="zig"></div>
      </div>
      <div class="inside-box">
        <p class="quote">
          <span class="drop">{{ quote.slice(0, 1) }}</span
          >{{ quote.slice(1, quote.length) }}
        </p>
        <p class="author">{{ author }}</p>
        <div class="triangle"></div>
        <div class="zigzag2">
          <div
            v-for="(zig, index) in zigzagsLong"
            :key="index"
            class="zig2"
          ></div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "",
  data() {
    return {
      quote:
        "I bought a seven-dollar pen because I always lose pens and I got sick of not caring.",
      author: "–Mitch Hedberg",
    };
  },
  computed: {
    zigzagsLong() {
      let results = [];
      for (let i = 0; i < 20; i++) {
        results.push(i);
      }
      return results;
    },
  },
};
</script>

<style scoped lang="scss">
.container {
  background: #999;
  color: black;
  height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
}
.quote {
  font-family: Georgia, "Times New Roman", Times, serif;
  font-size: 2.2rem;
  line-height: 3rem;
}

.drop {
  // font-size: 6rem;
  // padding-top: 20px;
  // padding-right: 10px;
  // margin-bottom: 120px;
  float: left;
  font-size: 7rem;
  line-height: 79px;
  padding-top: 8px;
  padding-right: 8px;
  padding-left: 3px;
}

.author {
  font-family: Georgia, "Times New Roman", Times, serif;
  font-size: 1.3rem;
  // margin-top: 1rem;
  text-align: right;
  transform: translateY(-0.6rem);
}

.box {
  background: white;
  padding: 2rem;
  width: 400px;
  height: 260px;
  z-index: 1;
}

.inside-box {
  border-top: black solid 7px;
  border-bottom: black solid 7px;
  padding: 20px 0;
  height: 80%;
  z-index: 2;
}

.triangle {
  width: 0px;
  height: 0px;
  // background: black;
  z-index: 50;
  transform: translate(-0.3rem, -1.3rem);
  border-left: 30px solid transparent;
  border-right: 30px solid transparent;
  border-bottom: 40px solid black;
}

.zigzag {
  display: flex;
  filter: blur(2px);
  transform: translateY(-22px);
  z-index: 0;
}

.zig {
  z-index: 50;
  transform: translate(-0.3rem, -1.3rem);
  border-left: 10px solid transparent;
  border-right: 10px solid transparent;
  border-bottom: 10px solid black;
}

.zigzag2 {
  display: flex;
  filter: blur(2px);
  transform: translateY(21px);
  z-index: 0;
}

.zig2 {
  z-index: 50;
  transform: translate(-0.3rem, -1.3rem);
  border-left: 10px solid transparent;
  border-right: 10px solid transparent;
  border-top: 10px solid black;
}
</style>
