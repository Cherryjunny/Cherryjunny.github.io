<template>
  <div class="menu">
    <a v-for="menu in menus" :key="menu">{{ menu }}</a>
  </div>

  <!-- Discount Component 사용-->
   <Discount :objData = "objData"/>

  <!-- Modal Component 사용-->
   <Modal @closeModal="modalStatus = false" :roomsInfo="roomsInfo" :currentProductNo="currentProductNo" 
    :modalStatus="modalStatus"/>

  <!-- Card Component 사용-->
   <Card @openModal="modalStatus = true; currentProductNo=$event" v-for="room in roomsInfo" :key="room.id" :room="room"
    :currentProductNo="currentProductNo" 
    :modalStatus="modalStatus"/>
  <!--모달(modal) 페이지 구성 -->.id
  <!-- <div class="black-bg" v-if="modalStatus == true">
    <div class="white-bg">
      <h4>상세페이지</h4>
      <img :src=roomsInfo[currentProductNo].image class="room-img">
      <p>{{roomsInfo[currentProductNo].title}}</p>
      <p>{{ roomsInfo[currentProductNo].content }}</p>
      <p>{{ roomsInfo[currentProductNo].price }}</p>
      <button @click="modalStatus = false">닫기</button>
    </div>
  </div> -->
  <!--<div v-for="(product, i) in products" :key="i">
    <img :src="require(`@/assets/room${i}.jpg`)" alt="room0" class="room-img">
    <h4 @click="modalStatus = true">{{ product }}</h4>
    <P>{{ price[i] }}만원</P>
    <button @click="increase">허위매물 신고</button>
        <span>신고 수 :{{ 신고수[i] }}</span> 
  </div>-->
  <!-- <div v-for="room in roomsInfo" :key="room.id">
    <img :src=room.image alt="room0" class="room-img">
    <h4 @click="modalStatus = true; currentProductNo = room.id">{{ room.title }}</h4>
    <P>{{ room.price }}원</P> 
  </div> -->
</template>

<script>
import data from "./assets/oneroom.js";
// import Discount from "./components/Discount.vue";
import Modal from "./components/Modal.vue";
import Card from "./components/Card.vue";

export default {
  name: 'App',

  data: () => ({
    objData : {name : "Kim", age : 20},
    currentProduct : 0,
    roomsInfo : data,
    menus : ['Home', 'Products', 'About'],
    products : ['역삼동원룸', '천호동원룸', '마포구원룸'],
    price : [50, 60, 70],
    신고수 : [0, 0, 0],
    status : true,
    modalStatus : false,
  }),
  methods : {
    increase(i){
      if(this.status == true){
        this.신고수[i += i]
        this.status = false
      
      } else{
        this.신고수[i] -= 1;
        this.status = true;
      }
    }
  },
  components : {
    //Discount,
    Modal,
    Card
  }
}
</script>
<style>
  div {
    box-sizing: border-box;
  }
  .black-bg{
    width: 100%;
    height: 600px;
    background: rgba(0,0,0,5);
    position: fixed;
    padding: 20px;
  }
  .white-bg{
    width: 100%;
    background: white;
    border-radius: 8px;
    padding: 20px;
  }
  .room-img {
    width: 100%;
    margin-top: 40px;
  }
  .menu {
    background: darkslateblue;
    padding: 15px;
    border-radius: 5px;
  }
  .menu a {
    color: white;
    padding: 10px;
  }

</style>