<template>
  <div class="banner-section1">
    <div class="container-fluid">
      <div class="banner-section">
        <div class="banner-title"></div>
      </div>
      <div
        id="slider"
        class="carousel slide carousel-fade"
        data-bs-ride="carousel"
      >
        <div class="carousel-inner banner-area">
          <div class="carousel-item active">
            <img
              src="../assets/phone/banner_1.jpg"
              class="d-block bannerhome rounded img-fluid"
              alt="..."
            />
          </div>
          <div class="carousel-item">
            <img
              src="../assets/phone/banner_2.jpg"
              class="d-block bannerhome rounded img-fluid"
              alt="..."
            />
          </div>
          <div class="carousel-item">
            <img
              src="../assets/phone/banner_3.jpg"
              class="d-block bannerhome rounded img-fluid"
              alt="..."
            />
          </div>
        </div>
        <button
          class="carousel-control-prev"
          type="button"
          data-bs-target="#slider"
          data-bs-slide="prev"
        >
          <span
            class="carousel-control-prev-icon reverse"
            aria-hidden="true"
          ></span>
          <span class="visually-hidden">Previous</span>
        </button>
        <button
          class="carousel-control-next"
          type="button"
          data-bs-target="#slider"
          data-bs-slide="next"
        >
          <span
            class="carousel-control-next-icon verse"
            aria-hidden="true"
          ></span>
          <span class="visually-hidden">Next</span>
        </button>
      </div>
    </div>
  </div>
</template>

<script>
// @ is an alias to /src
export default {
  name: "HomeView",
  components: {},
  data() {
    return {};
  },
};
</script>

<style lang="scss">
@import "../assets/_variables.scss";
.banner-section1 {
  width: 100%;
  background-image: url(../assets/phone/banner-bg-img.png);
  background-size: cover;
  background-repeat: no-repeat;
  position: relative;
  z-index: 1;
  top: 0;
  left: 0;
  min-height: 100vh;
  max-height: 999px;
  background-size: 100%;
  display: flex;
}
.img-banner {
  width: auto;
  height: auto;
}
.bannerhome {
  padding-left: 60px;
  padding-right: 60px;
}

.banner-title {
  h2 {
    font-weight: 700;
  }
}
#slider {
  position: relative;
  width: 100%;
  overflow: hidden;
  margin-top: 400px;
  padding: 20px;
}
img {
  vertical-align: middle;
}
.reverse {
  background-color: #030303;
  font-size: 50px;
}
.verse {
  background-color: #030303;
  font-size: 50px;
}
</style>
