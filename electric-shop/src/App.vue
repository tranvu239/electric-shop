<template>
  <header-app />

  <router-view v-on:add-to-cart="addToCart" />
  <footer-app />
</template>
<script>
import HeaderApp from "./components/HeaderApp.vue";
import FooterApp from "./components/FooterApp.vue";

export default {
  name: "App",
  components: {
    HeaderApp,
    FooterApp,
  },
  data() {
    return {
      products: [
        {
          id: 1,
          name: "Harry Potter series",
          price: 150000,
          img: "HP.png",
        },
        {
          id: 2,
          name: "Sherlock Holmes for kids",
          price: 300000,
          img: "SH.jpg",
        },
        {
          id: 3,
          name: "Tự truyện Luka Modric",
          price: 500000,
          img: "LM.png",
        },
        {
          id: 4,
          name: "Tự truyện Michael Carrick",
          price: 400000,
          img: "MC.jpg",
        },
        {
          id: 5,
          name: "Tự truyện Andrés Iniesta",
          price: 150000,
          img: "AI.jpg",
        },
        {
          id: 6,
          name: "All Quiet on the Western Front",
          price: 300000,
          img: "AQWF.jpg",
        },
        {
          id: 7,
          name: "Twilight series",
          price: 500000,
          img: "T.jpg",
        },
        {
          id: 8,
          name: "The Hunger Games trilogy",
          price: 400000,
          img: "HG.jpg",
        },
        {
          id: 9,
          name: "The Lord of the Rings trilogy",
          price: 500000,
          img: "LOTR.jpg",
        },
        {
          id: 10,
          name: "Percy Jackson series",
          price: 400000,
          img: "PJ.jpg",
        },
        {
          id: 11,
          name: "Chicken soup for the soul",
          price: 150000,
          img: "CSFTS.jpg",
        },
        {
          id: 12,
          name: "Game of Thrones series",
          price: 300000,
          img: "GOT.jpg",
        },
      ],
      cart: [],
    };
  },
  methods: {
    storeCart() {
      localStorage.setItem("cart", JSON.stringify(this.cart));
    },
    addToCart(data) {
      let product = this.products.find((p) => p.id == data.productId);
      if (this.cart.find((prod) => prod.id === product.id)) {
        const index = this.cart.findIndex((prod) => prod.id === product.id);
        this.cart[index] = {
          ...this.cart[index],
          addedQuantity: this.cart[index].addedQuantity + data.totalItems,
        };
      } else {
        product = { ...product, addedQuantity: data.totalItems };
        this.cart.push(product);
      }
      this.storeCart();
    },
  },
};
</script>
<style lang="scss">
@import url("https://cdn.jsdelivr.net/npm/bootstrap-icons@1.11.1/font/bootstrap-icons.css");
@import url("https://fonts.googleapis.com/css2?family=Josefin+Sans:wght@100;400&display=swap");
#app {
  font-family: "Josefin Sans", sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
* {
  font-family: "Josefin Sans", sans-serif;
}
nav {
  padding: 30px;

  a {
    font-weight: bold;
    color: #2c3e50;

    &.router-link-exact-active {
      color: #42b983;
    }
  }
}
</style>
