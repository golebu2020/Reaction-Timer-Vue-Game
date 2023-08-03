<template>
  <div class="resultDisplay">
    <div>Reaction Timer: {{ score }} ms</div>
    <div class="rank">{{ rank }}</div>
  </div>
</template>

<script>
export default {
  props: ["score"],
  data() {
    return {
      rank: null,
    };
  },
  mounted() {
    if (this.score < 250) this.rank = "Ninja Fingers";
    else if (this.score < 400) this.rank = "Rapid Reflexes";
    else this.rank = "Snail pace...";
  },
};
</script>

<style scoped>
@import url("https://fonts.googleapis.com/css2?family=Rubik:ital,wght@0,400;0,500;0,600;0,700;1,300&display=swap");
.resultDisplay {
  font-family: "Rubik", monospace;
  margin-top: 50px;
  background: #444;
  color: #fff;
  width: 40vw;
  height: 40vh;
  font-weight: 700;
  font-size: 20px;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  border-style: none;
  border-radius: 10px;
  box-shadow: 2px 10px 20px 10px rgba(0, 0, 0, 0.25);
}

.rank {
  font-size: 1.4em;
  color: #0faf87;
  font-weight: bold;
}
</style>
