# vuejs 설치

```
mkdir VUEJS

code .
```

vue cdn 추가

```vue
<script src="https://cdn.jsdelivr.net/npm/vue/dist/vue.js"></script>
```

```vue
<div id="app">
    {{name}}
    <input type="text" v-model="inputText">
    <p>{{ inputText }}</p>
</div>
<script>
   const app = new Vue({
        el: '#app', //어디에 올라갈것인가
        data: { //data 객체의 형태로
            name: 'minkyeong'
            inputText: ''
        }
    })
</script>
```

