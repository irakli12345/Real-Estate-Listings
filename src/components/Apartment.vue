<template>
  <div :class="{ onSaleDecorations: apartmentDetails.onSale }">
    <h3>{{ apartmentDetails.catchyName }}</h3>
    <img
      v-if="onSale"
      class="sale-icon"
      src="https://cdn1.iconfinder.com/data/icons/marketing-17/42/8_sale_ribbon_offer_label_sticker_tag_shopping-512.png"
    />
    <input
      type="checkbox"
      id="salecheckbox"
      @change="handleInputChange"
      :checked="apartmentDetails.onSale"
    />
    <label for="salecheckbox"> On Sale</label>
    <h3>{{ apartmentDetails.location }}</h3>
    <h3>{{ apartmentDetails.spaceInSquareMeters }}</h3>
    <img :src="apartmentDetails.image" />
  </div>
</template>

<script>
export default {
  name: "Apartment",
  props: {
    apartmentDetails: Object,
  },
  data() {
    return {};
  },
  computed: {},
  methods: {
    handleInputChange() {
      this.$emit("saleChange");
    },
  },
};
</script>

<style scoped>
img {
  height: 200px;
  width: 200px;
  object-fit: cover;
}
.onSaleDecorations {
  border: 5px solid goldenrod;
}
div {
  width: 30%;
  margin: auto;
}
.sale-icon {
  height: 100px;
  width: 100px;
  display: block;
  margin: auto;
}
label,
input {
  display: inline-block;
}
</style>
