<template>
  <div>
    <div v-for="gif in gifs" :key="gif.id">
      {{ gif.url }}
      <img :src="gif.images.original.url" />
    </div>
  </div>
</template>

<script>
export default {
  props: ['gifs'],
}
</script>

<style lang="scss" scoped></style>
