<template>

  <div class="menu">
    <a v-for="(menu_link,i) in menus" :key="i">{{menu_link}}</a>
  </div>

  <img alt="Vue logo" src="./assets/logo.png">

  <div v-for="(div_products,i) in products" :key="i">
    <h4>{{div_products[0]}}</h4>
    <p>{{div_products[1]}} 만원</p>
  </div>
  
</template>

<script>


export default {
  name: 'App',
  data(){
    return{
      products : {0:['역삼동원룸',60], 1:['천호동원룸',70], 2:['마포구원룸',80]},
      menus : ['Home', 'Products', 'About'],
    }
  },
  components: {
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
}

.menu{
  background: darkslateblue;
  padding: 15px;
  border-radius: 5px;
}
.menu a {
  color: white;
  padding: 10px;
}
</style>
