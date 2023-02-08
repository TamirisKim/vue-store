<template>
  <div class="v-main-wrapper">other {{ title }}
    <v-cart/>
    <v-catalog/>
  </div>
</template>

<script>
import vCatalog from './v-catalog'
import vCart from './v-cart'


export default {
  name: "v-main-wrapper",
  components: {
    vCatalog,
    vCart,
  },
  props: {}, //свойство перед от родит к детю
  data() {
    return {
      title: "Main wrapper",
    };
  }, //свойство перед от детя
  computed: {}, //вычесл
  methods: {}, //  отлав дейс польз (клиуки, анимац)
  watch: {}, //следить за измен чегото
  mounted() {
    console.log("onMounted");
  },
};
</script>

<style>
.v-main-wrapper {
  margin: 0 auto;
}
</style>
