<template>
  <div @click="stopTimer" class="block" v-if="showBlock">Click me</div>
</template>

<script>
export default {
  props: ["delay"],
  data() {
    return {
      showBlock: false,
      time: null,
      reactionTime: 0,
    };
  },
  mounted() {
    setTimeout(() => {
      this.showBlock = true;
      this.startTimer();
    }, this.delay);
  },

  methods: {
    startTimer() {
      this.timer = setInterval(() => {
        this.reactionTime += 10;
      }, 10);
    },
    stopTimer() {
      clearInterval(this.timer);
      console.log(this.reactionTime);
      this.$emit("end", this.reactionTime);
    },
  },
};
</script>

<style scoped>
.block {
  margin-top: 10px;
  display: flex;
  justify-content: center;
  align-items: center;
  width: 50vw;
  height: 50vh;
  background-color: darkgreen;
  color: whitesmoke;
  box-shadow: 5px 10px 10px 10px rgba(0, 0, 0, 0.12);
  border-style: solid;
  border-radius: 10px;
  border-width: 0;
  cursor: pointer;
}
</style>
