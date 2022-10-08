<template>
  <div class="details">
    <div class="container">
      <div class="row">
        <div
          class="col-md-12"
          v-for="(product, index) in products"
          :key="index"
        >
          <div v-if="proId == product.productId">
            <h1>{{ product.productTitle }}</h1>
            <img
              :src="product.image"
              class="img-fluid"
              width="600px"
              height="500px"
            />
          </div>
        </div>
      </div>
    </div>
  </div>
</template>
<script>
export default {
  name: "details",
  data() {
    return {
      proId: this.$route.params.Pid,
      title: "details",
      products: [
        {
          productTitle: "Beef Food",
          image: require("../assets/images/food7.jpg"),
          productId: 1,
        },
        {
          productTitle: "Duck Food",
          image: require("../assets/images/food2.jpeg"),
          productId: 2,
        },
        {
          productTitle: "Chinese Food",
          image: require("../assets/images/food3.jpg"),
          productId: 3,
        },
        {
          productTitle: "Traditional Dishes Food",
          image: require("../assets/images/food4.jpg"),
          productId: 4,
        },
        {
          productTitle: "Japanese Food",
          image: require("../assets/images/food5.jpg"),
          productId: 5,
        },
        {
          productTitle: "Sea Food",
          image: require("../assets/images/food6.jpg"),
          productId: 6,
        },
      ],
    };
  },
};
</script>

<style scoped>
img {
  border-radius: 10px;
}
</style>