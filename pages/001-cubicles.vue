<template>
  <div class="grid">
    <!-- {{ injectRandomQuote }} -->
    <div v-for="cell in injectRandomQuote" key="cell.id" class="cell">
      <div
        v-if="cell.content !== ''"
        class="quote"
        :style="{
          border: `${cell.style}`,
        }"
      >
        <h3>{{ cell.content.quote }}</h3>
        <h6>{{ cell.content.author }}</h6>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "cubicles",
  data() {
    return {
      cells: [0, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11],
      author: "Bill Burr",
      quote:
        "You know what a cubicle basically says? It basically says, like, 'You know what? We don't think you're smart enough for an office, but we don't want you to look at anybody.",
    };
  },
  computed: {
    cellsAsObjects() {
      let tables = [];
      for (let i = 0; i < this.cells.length; i++) {
        tables.push({ id: i, content: "", style: "" });
      }
      return tables;
    },
    injectRandomQuote() {
      let spot = Math.floor(Math.random() * this.cells.length);

      for (let i = 0; i < this.cells.length; i++) {
        if (i === spot) {
          this.cellsAsObjects[i].style = "5px dotted black";
          this.cellsAsObjects[i].content = {
            quote: this.quote,
            author: this.author,
          };
        }
      }
      return this.cellsAsObjects;
    },
  },
};
</script>

<style scoped lang="scss">
* {
  //   border: 1px solid red;
}
.grid {
  padding: 10px;
  background-color: gray;
  height: 100vh;
  width: auto;
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  grid-template-rows: repeat(4, 1fr);

  .cell {
    border: 2px dotted white;
  }

  .quote {
    padding: 7px;
    box-shadow: inset 5px 5px 10px #444;
  }

  p {
    font-family: "Georgia", sans-serif;
    color: blue;
    margin: 0px;
  }
}
</style>
