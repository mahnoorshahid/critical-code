<template>
  <div>
    <form @submit.prevent="getGifs">
      <input id="gifSerach" v-model="searchTerm" type="text" name="gifSearch" />
      <input id="button" type="submit" value="GIFs for YOU!" />
    </form>
    <!-- {{ ip }} -->
    <GifList :gifs="gifs" />
  </div>
</template>

<script>
import GifList from '@/components/GifList.vue'
export default {
  components: {
    GifList,
  },
  // async asyncData({ $axios }) {
  //   const ip = await $axios.$get(
  //     'https://api.giphy.com/v1/gifs/search?api_key=rrimiRdnKDDyN3lgC2jLH7L6dOwEW8LI&q=cats&limit=25&offset=0&rating=g&lang=en'
  //   )
  //   return { ip }
  // },
  data() {
    return {
      searchTerm: null,
      gifs: null,
      /* eslint-disable no-unused-vars */
    }
  },
  methods: {
    async getGifs() {
      /* eslint-disable no-unused-vars */
      const results = await this.$axios
        .$get(
          'https://api.giphy.com/v1/gifs/search?api_key=rrimiRdnKDDyN3lgC2jLH7L6dOwEW8LI&q=' +
            this.searchTerm
        )
        .then((response) => {
          console.log(response)
          this.gifs = response.data
        })
    },
  },
}
</script>

<style lang="scss" scoped></style>

// rrimiRdnKDDyN3lgC2jLH7L6dOwEW8LI
