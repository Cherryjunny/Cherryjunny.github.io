<template>
  <div>
    <img :src=room.image class="room-img">
    <h4 @click="$emit('openModal', room.id)">{{ room.title }}</h4>
    <P>{{ room.price }}원</P> 
  </div>
</template>

<script>
export default {
    name : "ProductCard",
    props : {
        //roomsInfo : Array,
        room : Object,
        currentProductNo : Number,
        modalStatus : Boolean,
    }
}
</script>

<style>

</style>