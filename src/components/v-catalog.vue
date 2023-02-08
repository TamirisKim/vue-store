<template>
  <div class="v-catalog">
    <v-catalog-item
      v-for="product in PRODUCTS"
      :key="product.article"
      :product_data="product"
      @sendArticle="showChaldArticle"
    />
  </div>
</template>

<script>
import vCatalogItem from "./v-catalog-item";
import { mapActions, mapGetters } from "vuex";

export default {
  name: "v-catalog",
  components: { vCatalogItem },
  props: {},
  data() {
    return {};
  },
  computed: {
    ...mapGetters(["PRODUCTS"]),
  },
  methods: {
    ...mapActions(["GET_PRODUCTS_FROM_API"]),

    showChaldArticle(data) {
      console.log(data);
    },
  },
  mounted() {
    this.GET_PRODUCTS_FROM_API()
    .then((response) => {
          if (response.data) {
            console.log('response')
          }
        })
  },
};
</script>

<style lang="scss">
.v-catalog {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
  gap: 20px;
  align-items: flex-start;
}
</style>
