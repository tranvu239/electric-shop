<template>
  <base-modal v-if="isShowModal" v-on:cancel="onOpenModal" title="Dang Nhap" />
  <nav
    class="navbar fixed-top navbar-expand-lg nav-dark"
    :class="{ changecolor: scrollPostition > 50 }"
  >
    <div class="container">
      <div class="navbar-brand">
        <router-link to="/">Bookstore</router-link>
      </div>
      <button
        class="navbar-toggler"
        type="button"
        data-bs-toggle="collapse"
        data-bs-target="#navbarSupportedContent"
        aria-controls="navbarSupportedContent"
        aria-expanded="false"
        aria-label="Toggle navigation"
      >
        <span class="navbar-toggler-icon"></span>
      </button>
      <div class="collapse navbar-collapse" id="navbarSupportedContent">
        <ul class="navbar-nav me-auto mb-2 mb-lg-0">
          <li class="nav-item">
            <router-link class="nav-link" to="/">Home</router-link>
          </li>

          <li class="nav-item">
            <router-link class="nav-link" to="/about">About</router-link>
          </li>

          <li class="nav-item">
            <router-link class="nav-link" to="/search">Search</router-link>
          </li>
        </ul>
        <ul class="navbar-nav text-center">
          <li class="nav-item">
            <button v-on:click="onOpenModal" class="nav-link">Dang nhap</button>
          </li>

          <li class="nav-item">
            <router-link class="nav-link" to="/cart">Cart</router-link>
          </li>

          <li class="nav-item">
            <router-link class="nav-link" to="">History</router-link>
          </li>
        </ul>
      </div>
    </div>
  </nav>
</template>

<script>
import BaseModal from "./BaseModal.vue";

export default {
  name: "HeaderApp",
  components: {
    BaseModal,
  },
  data() {
    return {
      isShowModal: false,

      scrollPostition: null,
    };
  },
  methods: {
    onOpenModal() {
      this.isShowModal = !this.isShowModal;
    },
    updateScroll() {
      this.scrollPostition = window.scrollY;
    },
  },
  mounted() {
    window.addEventListener("scroll", this.updateScroll);
  },
};
</script>

<style lang="scss">
.navbar {
  display: flex;
  justify-content: center;
  justify-items: center;
  align-items: center;
  font-weight: 600;
}
.changecolor {
  background-color: white;
}
.navbar-brand {
  transform: translateX(-50%);
  left: 50%;
  position: absolute;
}
</style>
