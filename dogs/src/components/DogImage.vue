<template>
    <div>
        <button @click="getDog">멍멍이 가져오기</button>
        <div v-for="image in images" v-bind:key="image.id">
            <img v-bind:src="image.url" alt="">
        </div>
    </div>
</template>

<script>
import axios from 'axios'

export default {
    name: 'DogImage',
    data() {
        return {
            title: 'Dog Image Generator',
            dog: "",
            images:[]
        }
    },
    methods: {
        getDog(){
            axios
            .get("https://dog.ceo/api/breeds/image/random")
            .then(res=>{
                this.images.push({
                    url: res.data.message,
                    id: Date.now()
                });
                //console.log(res.data.message);
            })
            
            //1. dog.ceo API에 요청을 보내어 JSON을 응답받아
            //2. image url을 가져와
            //3. <img src=""로 넣어줌>
        }
    }
}
</script>

<style>

</style>