<template>
  <div class="container">
    <div className="quote">
      <p
        class="word"
        v-for="word in quoteArrayCatalog"
        :key="word.id"
        :style="{
          fontSize: `${word.fontSize * 8 + 10}px`,
          fontWeight: `${word.fontWeight}`,
          transform: `rotate(${word.rotation}deg)`,
        }"
      >
        {{ word.text }}
      </p>
      <p>
        <i>–{{ author }}</i>
      </p>
    </div>
  </div>
</template>

<script>
export default {
  name: "002-coffee",
  data() {
    return {
      quote:
        "Every morning I get up and make instant coffee and I drink it so I have the energy to make real coffee.",
      author: "Steven Wright",
      fontWeights: [100, 200, 300, 400, 500, 600, 700, 800, 900],
    };
  },
  computed: {
    quoteArrayCatalog() {
      let arr = this.quote.split(" ");
      let catalog = [];
      for (let i = 0; i < arr.length; i++) {
        catalog.push({
          id: i,
          text: arr[i],
          fontSize: Math.floor(Math.random() * 12),
          rotation: Math.floor(Math.random() * 10),
          fontWeight:
            this.fontWeights[
              Math.floor(Math.random() * this.fontWeights.length)
            ],
        });
      }
      return catalog;
    },
  },
  methods: {},
};
</script>

<style scoped lang="scss">
* {
  // border: 1px solid black;
}

.container {
  height: 100vh;
  background: brown;
  padding: 20px;

  .quote {
    display: flex;
    flex-direction: row;
  }

  p {
    color: white;
    font-size: 4vw;
    display: inline-block;
  }
}
</style>
