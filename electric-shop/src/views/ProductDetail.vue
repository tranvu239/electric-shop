<template>
  <div class="container cart-area">
    <div class="row">
      <div class="col col-lg-6">
        <div id="carouselExampleIndicators" class="carousel slide">
          <div class="carousel-indicators">
            <button
              type="button"
              data-bs-target="#carouselExampleIndicators"
              data-bs-slide-to="0"
              class="active"
              aria-current="true"
              aria-label="Slide 1"
            ></button>
            <button
              type="button"
              data-bs-target="#carouselExampleIndicators"
              data-bs-slide-to="1"
              aria-label="Slide 2"
            ></button>
            <button
              type="button"
              data-bs-target="#carouselExampleIndicators"
              data-bs-slide-to="2"
              aria-label="Slide 3"
            ></button>
          </div>
          <div class="carousel-inner">
            <div class="carousel-item active">
              <img
                :src="require(`../assets/${currentProduct.img}`)"
                class="d-block w-100 img-fluid detail-img rounded"
                alt="..."
              />
            </div>
            <div class="carousel-item">
              <img
                src="../../public/white.png"
                class="d-block w-100 img-fluid detail-img rounded"
                alt="..."
              />
            </div>
            <div class="carousel-item">
              <img
                src="../../public/grey.png"
                class="d-block w-100 img-fluid detail-img rounded"
                alt="..."
              />
            </div>
          </div>
          <button
            class="carousel-control-prev"
            type="button"
            data-bs-target="#carouselExampleIndicators"
            data-bs-slide="prev"
          >
            <span class="carousel-control-prev-icon" aria-hidden="true"></span>
            <span class="visually-hidden">Previous</span>
          </button>
          <button
            class="carousel-control-next"
            type="button"
            data-bs-target="#carouselExampleIndicators"
            data-bs-slide="next"
          >
            <span class="carousel-control-next-icon" aria-hidden="true"></span>
            <span class="visually-hidden">Next</span>
          </button>
        </div>
      </div>
      <div class="col col-lg-6">
        <div class="card mt-4" style="width: auto">
          <div class="card-body">
            <h5 class="card-title">{{ currentProduct.name }}</h5>
            <h6 class="card-subtitle mb-2 text-body-secondary">
              {{ currentProduct.price }}
            </h6>
            <p class="card-text">
              Product description Some quick example text to build on the card
              title and make up the bulk of the card's content.
            </p>
            <div class="row function-area">
              <div class="col-6">
                <div class="cart-button">
                  <button
                    type="button"
                    class="btn btn-outline-dark btn-plus"
                    @click="increaseTotal"
                  >
                    +
                  </button>
                  <span class="quantity p-2">{{ total }}</span>
                  <button
                    type="button"
                    class="btn btn-outline-dark btn-minus"
                    @click="decreaseTotal"
                  >
                    -
                  </button>
                </div>
              </div>
              <div class="col-6">
                <router-link to="/cart">
                  <button
                    type="button"
                    class="btn btn-outline-success"
                    @click="addToCartHandler"
                  >
                    Add to Cart
                  </button></router-link
                >
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>
<style lang="scss" scoped>
img {
  height: 300px;
  width: auto;
}
.cart-area {
  display: flex;
  padding-top: 12vh;
  top: 0;
  min-height: 70vh;
}
.detail-img {
  object-fit: contain;
}

.function-area {
  padding-left: 100px;
  padding-right: 100px;
}
</style>
<script>
export default {
  name: "ProductDetail",
  components: {},
  data() {
    return {
      total: 1,
      name: "",
      isShowModal: false,
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
    };
  },
  methods: {
    addToCartHandler() {
      const data = {
        productId: this.currentProduct.id,
        totalItems: this.total,
      };
      this.$emit("add-to-cart", data);
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
    this.id = this.$route.params.product_id;
  },
  computed: {
    currentProduct() {
      const id = this.$route.params.product_id;
      const product = this.products.find((p) => p.id == id);
      return product;
    },
  },
};
</script>
