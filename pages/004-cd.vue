<template>
  <section>
    <div class="quote">
      <p>
        This CD is going to be in stores. The only way I could get my old CD in
        a store is if I would take one in and leave it.
      </p>
      <p><i>Mitch Hedberg</i></p>
    </div>
    <div class="circle-container">
      <div
        v-for="ring in rings"
        :key="ring"
        class="circle"
        :style="{
          height: `${ring * 25}px`,
          width: `${ring * 25}px`,
          zIndex: `${-ring + 20}`,
          background: `linear-gradient(45deg, rgb(${
            ring + Math.floor(Math.random() * 100)
          }, 100, 20), rgb(100, ${
            ring + Math.floor(Math.random() * 100)
          }, 100))`,
        }"
      ></div>
    </div>
  </section>
</template>

<script lang="ts">
export default {
  name: "q004",
  data() {
    return {
      rings: [
        0, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15, 16, 17, 18, 19,
        20, 21, 22, 23, 24,
      ],
    };
  },
  computed: {
    ringReversed() {
      return this.rings.reverse();
    },
  },
};
</script>

<style scoped lang="scss">
section {
  background: #444;
  height: 100vh;
}

.circle {
  // border: 1px #333 solid;
  border-radius: 50%;
  position: absolute;
  height: 100%;
  width: 100%;
  // background: linear-gradient(45deg, #333, #bbb);
}

.circle-container {
  // border: 1px solid red;
  height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
}

.quote {
  position: absolute;
  color: white;
  top: 10%;
  left: 20%;
  font-size: 4rem;
  font-weight: 100;
  z-index: 1000;
}
</style>
