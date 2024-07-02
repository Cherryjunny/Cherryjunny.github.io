<template>
  
  <div class="discount">
    <h4>지금 결제하면 20% 할인</h4>
    <!-- <h6>{{ objData }}</h6> -->
  </div>
</template>

<script>
export default {
    name : "DiscountBanner",
    props : {
        objData : Object,
    }
}
</script>

<style>

 .discount {
    background: #eee;
    padding: 10px;
    margin: 10px;
    border-radius: 5px;
  }

</style>