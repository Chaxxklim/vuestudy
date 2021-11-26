<template>
  <div class="black-bg" v-if="모달창열렸니==true">
    <div class="white-bg">
      <h4>{{products[누른거].title}}</h4>
      <p>{{ products[누른거].content }}</p>
      <p>{{products[누른거].price}}원</p>
      <button v-on:click="모달창열렸니=false">닫기</button>
    </div>
  </div>

  <div class="menu">
    <a v-for="i in 메뉴들" :key="i">{{i}}</a>
  </div>

  <div v-for="(a,i) in products" :key="i">
    <img :src="a.image">
    <h4 @click="모달창열렸니 = true; 누른거 = i">{{a.title}}</h4>
    <p>{{ a.price }}원</p>
  </div>

</template>

<script>

import oneroom from './assets/oneroom.js';



export default {
name: 'App',
  components: {

  },
  data(){
    return{
      누른거 : 0,
      모달창열렸니 : false,

      products : oneroom,
      메뉴들 : ['Home','Shop','About'],
      신고수 : 0

    }
  },
  methods : {
   increase(){
    this.신고수 += 1;
   }
  }
}
</script>

<style>
body{
  margin : 0;
}
div{
  box-sizing: border-box;
}
.menu{
  background: darkslateblue;
  padding: 15px;
  border-radius: 5px;

}
.menu a{
  color: white;
  padding: 10px;
}
.black-bg{
  width : 100%; height : 100%;
  background: rgba(0,0,0,0.5);
  position: fixed; padding: 20px;
}
.white-bg{
  width : 100%; background: white;
  border-radius: 8px;
  padding: 20px;
}
</style>
