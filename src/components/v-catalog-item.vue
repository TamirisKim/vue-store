<template>
  <div class="v-catalog-item">
   <img class="v-catalog-item__image" :src=" require('../assets/images/' + product_data.image) " alt="img">
    <p>{{ product_data.name }}</p>
    <p>Price ${{ product_data.price }}</p>
    <button @click="addToCart">Add to cart</button>
  </div>
</template>
<script>
export default {
  name: "v-catalog-item",
  components: {},
  props: {product_data:{
   type: Object,
   default(){
      return {}
   }
   
  }},
  data() {
    return {};
  },
  methods: {
    addToCart(){
      this.$emit("addToCart", this.product_data);
    }
  }
};
</script>

<style lang="scss">
.v-catalog-item {
  box-shadow: 0 0 8px 0 #e0e0e0;
  padding: $padding * 2;
  &__image{
   width: 100px;
  }
}
</style>
