<template>
  <div class="row align-items-center d-flex">
    <div class="col-auto action-item">
      <div @click="addProduct(product.id)" class="text-dark">
        <i class="fas fa-2x fa-plus"></i>
      </div>
    </div>
    <div class="col">
      <p class="card-text fs-6">{{ product.name }} </p>
    </div>
    <div class="col">
      <span class="mb-0">العدد</span>
      <p class="card-text fs-6"><b>{{ product.inCount }}</b></p>
    </div>
    <div class="col-md d-none d-md-block">
      <span class="mb-0">الإجمالي</span>
      <p class="card-text fs-6"><b>{{ $n(product.price, 'currency') }}</b></p>
    </div>
    <div class="col-auto">
      <div @click="removeProduct(product.id)" class="action-item text-danger">
        <i v-if="product.inCount > 1" class="fas fa-2x fa-minus"></i>
        <i v-else class="fas fa-2x fa-trash"></i>
      </div>
    </div>
  </div>
</template>

<script>
import { mapMutations, mapGetters, mapActions } from "vuex";

export default {
  props: ["product", "orderIndex"],
  data() {
    return {};
  },
  methods: {
    ...mapActions({
      addProduct: "supermarket/orders/addProduct",
      removeProduct: "supermarket/orders/removeProduct",
    }),
  },
};
</script>

<style lang="scss" scoped>
</style>