<template>
  <div>
    <button @click="getCat">고양이 가져오기</button>
    <div v-for="image in images" :key="image.id">
      <img width="200" height="200" :src="image.url" alt="">
    </div>
  </div>
</template>

<script>
import axios from 'axios'
export default {
  name: 'CatImage',
  data() {
    return {
      title: 'Dog Image Generator',
      source: '',
      images: []
    }
  },
  methods: {
    getCat() {
      axios.get('https://api.thecatapi.com/v1/images/search')
        .then(response => {
          console.log(response.data[0].url)
          this.images.push({
            id: Date.now(),
            url: response.data[0].url
          })
        })
    }
  }
}
</script>

<style>
</style>