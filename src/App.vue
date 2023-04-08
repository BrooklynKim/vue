<template>

<div class="black-bg" v-if="모달창열렸니 == true">
  <div class="white-bg">
    <h4>상세페이지임</h4>
    <p>상세페이지 내용임</p>
    <button @click="모달창열렸니 = false">닫힘</button>
  </div>
</div>



<div class="menu">
    <a v-for="i in 메뉴들" :key="i">{{i}}</a>
    <!--i는 아무 이름이나 해도 괜찮다-->
  </div>


  <!--
    <div>
      <h4>{{ products[0] }}</h4>
      <p> {{ price1 }} 만원</p>

      <h4>{{ products[1] }}</h4>
      <p> {{ price2 }} 만원</p>

      <h4>{{ products[2] }}</h4>
      <p> {{ price2 }} 만원</p>
    </div>
   -->
  <!--
   <div v-for="(a,i) in products" :key="i">
    <h4>{{ a }}</h4>
    <p>50만원</p>
   </div>
   --> 

   <div>
    <img src="./assets/room0.jpg" class="room-img">
    <h4 @click="모달창열렸니 = true">{{ products[0] }}</h4>
    <p>50만원</p>
    <!--<button v-on:click="신고수++">허위매물신고</button> <span>신고수 : {{ 신고수 }}</span>-->
    <!--<button v-on:click="신고수+=1">허위매물신고</button> <span>신고수 : {{ 신고수 }}</span>-->
    <!--<button @mouseover="신고수++">허위매물신고</button> <span>신고수 : {{ 신고수 }}</span>-->
    <!--<button @mouseover="increase()">허위매물신고</button> <span>신고수 : {{ 신고수 }}</span>-->
    <button v-on:click="신고수[0]++">허위매물신고</button> 
    <span>신고수 : {{ 신고수[0] }}</span>
   </div>

   <div>
    <img src="./assets/room1.jpg" class="room-img">
    <h4>{{ products[1] }}</h4>
    <p>60만원</p>
    <button @click="신고수[1]++">허위매물신고</button>
    <span>신고수 : {{ 신고수[1] }}</span>
   </div>

   <div>
    <img src="./assets/room2.jpg" class="room-img">
    <h4>{{ products[2] }}</h4>
    <p>70만원</p>
    <button v-on:click="신고수[2]++">허위매물신고</button>
    <span>신고수 : {{ 신고수[2] }}</span>
   </div>
</template>

<script>

export default {
  name: 'App',
  data(){ //state라고 한다.
      return{
        모달창열렸니 : false,//true또는 0 아무거나...   false 닫혔다, true 열렸다.
        신고수 : [0,0,0],
        메뉴들 : ['Home','Shop','About'],
        price : ['70','30'],
        products : ["역삼동원룸","천호동원룸","마포구원룸"],
      }
    },
    methods : {
      increase(){
        this.신고수 += 1;
      },
      increase2(){

      }

    },
  components: {
    
  }
}
</script>

<style>
body{
  margin: 0;
}
div{
  box-sizing: border-box;
}
.black-bg{
  width: 100%; height: 100%;
  background: rgba(0,0,0,0.5);
  position: fixed; padding: 20px;
}
.white-bg{
  width: 100%; background: white;
  border-radius: 8px;
  padding: 20px;
}


.room-img{
  width: 100%;
  margin-top: 40px;
}

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

.menu{
  background : darkslateblue;
  padding : 15px;
  border-radius : 5px;
}
.menu a{
  color : white;
  padding : 10px;
}

</style>
