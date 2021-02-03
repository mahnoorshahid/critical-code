<template>
  <div v-if="goodbye" class="container">
    <input type="checkbox" v-model="goodbye" name="goodbye" />
    <label for="goodbye">goodbye</label>
    <h1>hello</h1>
    <div v-bind:class="goodbye">
      {{ goodbye ? tacos[0] : tacos[1] }}
    </div>
  </div>
  <!-- <div v-for="taco in tacos" v-bind:key="taco">
      <p> {{taco}}</p>
    </div> -->
</template>

<script>
export default {
  data() {
    return {
      goodbye: true,
      tacos: ['al pastor,', 'somethings'],
    }
  },
}
</script>

<style scoped>
.container {
  margin: 0 auto;
  min-height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
  text-align: center;
}
</style>
