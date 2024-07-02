<template>
  <div class="black-bg" v-if="this.modalStatus == true">
    <div class="white-bg">
      <h4>상세페이지</h4>
      <img :src=roomsInfo[currentProductNo].image class="room-img">
      <p>{{roomsInfo[currentProductNo].title}}</p>
      <p>{{ roomsInfo[currentProductNo].content }}</p>
      <p>{{ roomsInfo[currentProductNo].price }}</p>
      <Discount />
      <button @click="$emit('closeModal')">닫기</button>
    </div>
  </div>
</template>

<script>
import Discount from "./Discount.vue";
export default {
    name : "ModalWindow",
    props : {
        roomsInfo : Array,
        currentProductNo : Number,
        modalStatus : Boolean,
    },
    components : {
      Discount,
    }
}
 
</script>

<style>

</style>