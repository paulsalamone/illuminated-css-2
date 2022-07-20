<template>
  <section>
    <div class="diamond-sea">
      <div v-for="diamond in diamonds" :key="diamond" class="diamond"></div>
    </div>
    <div class="diamond-sea2">
      <div v-for="diamond in diamonds" :key="diamond" class="diamond2"></div>
    </div>
    <div class="quote-div">
      <p class="quote">
        I don't exercise. If God had wanted me to bend over, he would have put
        diamonds on the floor.
      </p>
      <p class="author"><i>Joan Rivers</i></p>
    </div>
  </section>
</template>

<script lang="ts">
export default {
  name: "q003",
  data() {
    return {
      diamonds: [
        0, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15, 16, 17, 18, 19,
        20, 21, 22, 23, 24,
      ],
    };
  },
};
</script>

<style scoped lang="scss">
section {
  // border: 1px solid red;
  box-shadow: inset 0 0 100px rgba(255, 255, 255, 0.16);
  width: 40em;
  height: 40em;
  position: absolute;
  left: 25%;
  margin: 5px;
}

.quote-div {
  position: absolute;
  top: 40%;
  left: 15%;
  right: 15%;
  text-align: center;
  text-shadow: 0px 0px 10px black;
}

.quote {
  color: white;
  font-family: Georgia, "Times New Roman", Times, serif;
  font-size: 1.7em;
  line-height: 1.4em;
  font-weight: 100;
  z-index: 10;
}

.author {
  color: white;
  font-size: 1em;
  font-family: Georgia, "Times New Roman", Times, serif;
  margin-top: 1em;
  font-weight: 100;
  letter-spacing: 0.1em;
  text-transform: uppercase;
  z-index: 10;
}

.diamond-sea {
  display: grid;
  grid-template-rows: repeat(5, 1fr);
  grid-template-columns: repeat(5, 1fr);
  // border: 2px solid orange;
  transform: translateX(30px) translateY(30px);
  height: 100%;
  width: 100%;
}
.diamond-sea2 {
  position: absolute;
  top: 10%;
  left: 10%;
  display: grid;
  grid-template-rows: repeat(5, 1fr);
  grid-template-columns: repeat(5, 1fr);
  // border: 2px solid orange;
  transform: translateX(30px) translateY(30px);
  height: 100%;
  width: 100%;
}

.diamond {
  background-color: white;
  // border: 30px solid black;
  box-shadow: inset 0 0 30px black, inset 0 0 10px black, inset 0 0 5px black;
  transform: rotate(45deg);
  opacity: 0.5;
  width: 33.33%;
  height: 33.33%;
  animation: swelling 5s linear infinite;
}

.diamond2 {
  background-color: white;
  // border: 30px solid black;
  box-shadow: inset 0 0 25px black, inset 0 0 7px black, inset 0 0 2px black;
  transform: rotate(45deg);
  width: 33%;
  height: 33%;
  animation: swelling2 7s linear infinite;
}

@keyframes swelling {
  0% {
    transform: scale(10%) rotate(45deg);
    opacity: 0.3;
  }

  40% {
    transform: scale(30%) rotate(45deg);
    opacity: 1;
  }

  100% {
    transform: scale(10%) rotate(45deg);
    opacity: 0.3;
  }
}

@keyframes swelling2 {
  0% {
    transform: scale(30%) rotate(45deg);
    opacity: 0.4;
  }

  50% {
    transform: scale(60%) rotate(45deg);
    opacity: 0.9;
  }

  100% {
    transform: scale(30%) rotate(45deg);
    opacity: 0.4;
  }
}
</style>
