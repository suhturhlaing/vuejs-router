<template>
  <div class="home">
    <h1>{{ title }}</h1>
    <div class="row">
      <div
        class="col-md-4 col-lg4"
        v-for="(data, index) in products"
        :key="index"
        @click="goTodetail(data.productId)"
      >
        <img :src="data.image" class="img-fluid" />
        <h3 @click="goTodetail(data.productId)">{{ data.productTitle }}</h3>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "home",
  data() {
    return {
      title: "Home",
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
  methods: {
    goTodetail(prodId) {
      let proId = prodId;
      this.$router.push({ name: "details", params: { Pid: proId } });
    },
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.row img {
  max-height: 15em;
  width: 100%;
  margin-bottom: 20px;
}
.row h3 {
  cursor: pointer;
  margin-bottom: 2rem;
}
.img-fluid {
  border-radius: 7px;
  box-shadow: 10px 10px 5px #f0f0f0;
}
</style>
