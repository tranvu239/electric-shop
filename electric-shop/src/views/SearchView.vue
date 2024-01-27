<template>
  <div class="search-area">
    <div class="container">
      <h1 class="title" id="header">Popular books</h1>

      <div class="row">
        <div class="col col-lg-2">
          <div class="card group" style="width: 10rem">
            <div class="card-header">Filter</div>
            <ul class="list-group list-group-flush">
              <li class="list-group-item group">
                <p class="filter-item">Mystery</p>
              </li>
              <li class="list-group-item group">
                <p class="filter-item">Romance</p>
              </li>
              <li class="list-group-item group">
                <p class="filter-item">Science fiction</p>
              </li>
              <li class="list-group-item group">
                <p class="filter-item">Fantasy</p>
              </li>
              <li class="list-group-item group">
                <p class="filter-item">Horror</p>
              </li>
              <li class="list-group-item group">
                <p class="filter-item">Adventure</p>
              </li>
              <li class="list-group-item group">
                <p class="filter-item">Historical</p>
              </li>
            </ul>
          </div>
        </div>

        <div class="col col-lg-9">
          <div class="row row-cols-1 row-cols-md-3 p-2">
            <div class="col" v-for="product in products" :key="product.id">
              <div class="card mb-2">
                <img
                  :src="require(`../assets/${product.img}`)"
                  class="card-img-top img-fluid"
                  alt=""
                />
                <div class="card-body">
                  <router-link :to="`product/${product.id}`">
                    <h6 class="card-title">{{ product.name }}</h6>
                  </router-link>

                  <p class="card-text">{{ product.price }}</p>
                  <p class="card-text">
                    This is a longer card with supporting text below as a
                    natural lead-in to additional content. This content is a
                    little bit longer.
                  </p>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
// @ is an alias to /src
export default {
  name: "SearchView",
  components: {},
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
    };
  },
  methods: {},
};
</script>
<style lang="scss" scoped>
@import "../assets/_variables.scss";
.search-area {
  display: flex;
  padding-top: 12vh;
  top: 0;
  background-size: cover;
  background: $search-bg;
  min-height: 70vh;
}

.card {
  height: 550px;
  width: auto;
}

.title:before {
  content: "";
  position: absolute;
  display: block;
  height: 2px;
  width: 200px;
  background: $black;
  left: 0;
  top: 15%;
}
.title:after {
  content: "";
  position: absolute;
  display: block;
  height: 2px;
  width: 200px;
  background: $black;
  right: 0;
  top: 15%;
}
.card-header {
  font-weight: 1000;
}
.filter-item {
  color: $grey;
  position: relative;
  transition: ease 0.3s;
  font-weight: 1000;
}
.filter-item:hover {
  color: $black;
}
.filter-item:hover:after {
  content: "";
  position: absolute;
  width: 100%;
  height: 5%;
  background: $blue;
  left: 0;
  bottom: 0;
}
.group {
  border: none;
}
.card-img-top {
  height: 300px;
  object-fit: contain;
  background-size: cover;
  width: auto;
}
</style>
