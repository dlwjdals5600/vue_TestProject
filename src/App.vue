<template>

<div class="black-bg" v-if="modalOpen">
    <div class="white-bg">
      <h4>상세페이지</h4>
      <p>상세페이지 내용</p>
      <button @click="modalOpen = False">닫기</button>
    </div>
</div>

  <div class="menu">
    <a v-for="(menu_link,i) in menus" :key="i">{{menu_link}}</a>
  </div>





  <img alt="Vue logo" src="./assets/logo.png">

  <div v-for="(div_products,i) in products" :key="i">
    <img :src="getImageSrc(div_products[0])" class="poket-img">
    <h4 @click="modalOpen = true">{{div_products[1]}}</h4>
    <p>{{div_products[2]}} 만원</p>
    <button @click="div_products[3]++">허위매물신고</button> <span>신고수 : {{div_products[3]}} </span>
  </div>
  
</template>

<script>


export default {
  name: 'App',
  data(){
    return{
      modalOpen : false,
      products : {0:['./assets/paori.jpg','파오리',60,0], 1:['./assets/sunder.jpg','썬더',70,0], 2:['./assets/crap.jpg','크랩',80,0]},   // [원룸이름, 가격, 허위매물신고수]
      menus : ['Home', 'Products', 'About'],
    }
  },
  methods :{
    getImageSrc(imagePath){
      return require(`${imagePath}`)
    }
  },

  components: {
  }
}
</script>

<style>
body {
  margin: 0
}
div {
  box-sizing: border-box;
}
.black-bg {
  width: 100%; height: 100%;
  background: rgba(0,0,0,0.5);
  position: fixed; padding: 20px;
}
.white-bg {
  width: 100%; background: white;
  border-radius: 8px;
  padding: 20px;
}
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
.poket-img {
  width: 20%;
  
}
</style>
