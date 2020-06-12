<template>
  <div id="app">
    <h1>Dog & Cat</h1>
    <Buttons @dogButtonClicked="getDog"/>
    <DogImage :dogImages="dogImages"/>
    <CatImage :catImages="catImages"/>
    
  </div>
</template>

<script>
import DogImage from './components/DogImage.vue'
import CatImage from './components/CatImage.vue'
import Buttons from './components/Buttons.vue'
import axios from 'axios'

export default {
  name: 'App',
  components: {
    DogImage,
    CatImage,
    Buttons
  },
  data(){
    return{
      catImages:[],
      dogImages:[]
    }
  },
  methods: {
    getDog() {
      axios.get('https://dog.ceo/api/breeds/image/random')
        .then(response => {
          console.log(response.data.message)
          this.dogImages.push({
            id: Date.now(),
            url: response.data.message
          })
        })
    },
    getCat() {
      axios.get('https://api.thecatapi.com/v1/images/search')
        .then(response => {
          console.log(response.data[0].url)
          this.catImages.push({
            id: Date.now(),
            url: response.data[0].url
          })
        })
    }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
