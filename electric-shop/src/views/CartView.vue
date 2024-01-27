<template>
  <place-order-modal
    v-if="isShowModal"
    v-on:cancel="onOpenModal"
    title="place order"
  />
  <div class="cart-area">
    <div class="container">
      <div class="row" v-for="product in cart" :key="product.id">
        <div class="col col-lg-9">
          <div class="card mb-3" style="max-width: auto">
            <div class="row">
              <div class="col">
                <img
                  :src="require(`../assets/${product.img}`)"
                  class="img-fluid img-cart"
                  alt="..."
                />
              </div>
              <div div class="col-md-8">
                <div class="card-body">
                  <h5 class="card-title">{{ product.name }}</h5>
                  <p class="card-text">
                    This is a wider card with supporting text below as a natural
                    lead-in to additional content. This content is a little bit
                    longer.
                  </p>
                  <p class="card-text">
                    <small class="text-body-secondary"
                      >Last updated 3 mins ago</small
                    >
                  </p>
                </div>
              </div>
            </div>
          </div>
        </div>

        <div class="col col-lg-3">
          <p>price</p>
          <h5>{{ separator(product.price) }}</h5>
          <div class="cart-button">
            <button
              type="button"
              class="btn btn-outline-dark btn-plus"
              @click="increaseTotal"
            >
              +
            </button>
            <span class="quantity">{{ product.addedQuantity }}</span>
            <button
              type="button"
              class="btn btn-outline-dark btn-minus"
              @click="decreaseTotal"
            >
              -
            </button>
          </div>
        </div>
      </div>
      <hr />
      <div class="row">
        <div class="col col-lg">coupon</div>
        <div class="col col-lg">
          <button class="btn-coupon">pick coupon</button>
        </div>
      </div>
      <hr />
      <div class="row">
        <table class="table table-dark table-striped">
          <thead>
            <tr>
              <th scope="col">Shipping cost</th>
              <td scope="col">389745632489563498531</td>
            </tr>
          </thead>
          <tbody>
            <tr>
              <th scope="row">Total cost</th>
              <td>{{ separator(totalPrice) }}</td>
            </tr>
          </tbody>
        </table>
        <div class="col col-lg-12">
          <button v-on:click="onOpenModal" class="place-order">
            place order
          </button>
        </div>
      </div>
    </div>
  </div>
</template>
<style lang="scss" scoped>
.cart-area {
  display: flex;
  margin-top: 15vh;
}
.cart-img {
  height: 80px;
  width: auto;
}
.card {
  border: 1px grey;
}
.cart-button {
  display: flex;
  align-items: center;
  justify-content: center;
  margin-top: 50px;
}
.quantity {
  padding: 10px;
}
.img-cart {
  border-radius: 10%;
}
.place-order {
  border-radius: 10%;
}
.btn-coupon {
  border-radius: 10%;
}
.err {
  border-radius: 30px;
}
</style>
<script>
import PlaceOrderModal from "@/components/PlaceOrderModal.vue";
export default {
  name: "CartView",
  components: {
    PlaceOrderModal,
  },
  data() {
    return {
      total: 1,
      name: "",
      isShowModal: false,
      cart: {},
    };
  },
  methods: {
    separator(numb) {
      var str = numb.toString().split(".");
      str[0] = str[0].replace(/\B(?=(\d{3})+(?!\d))/g, ",");
      return str.join(".");
    },
    onOpenModal() {
      this.isShowModal = !this.isShowModal;
    },
    increaseTotal() {
      this.total++;
    },
    decreaseTotal() {
      if (this.total > 1) {
        this.total--;
      }
    },
  },
  mounted() {
    this.name = this.$route.params.product_name;
    this.cart = JSON.parse(localStorage.getItem("cart"));
  },
  computed: {
    totalPrice() {
      let totalValue = 0;

      Object.values(this.cart).forEach(
        (product) => (totalValue += product.price * product.addedQuantity)
      );
      return totalValue;
    },
  },
};
</script>
