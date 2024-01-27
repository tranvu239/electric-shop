<template>
  <div class="modal" v-on:click="onCloseModal" tabindex="-1">
    <div class="modal-dialog" v-on:click.stop="">
      <div class="modal-content">
        <div class="modal-header">
          <h5 class="modal-title">{{ title }}</h5>
          <button
            v-on:click="onCloseModal"
            type="button"
            class="btn-close"
            data-bs-dismiss="modal"
            aria-label="Close"
          ></button>
        </div>
        <div class="modal-body">
          <div class="card" style="width: 15rem, length: auto">
            <div class="card-body">
              <label for="inputUsername" class="form-label">Username</label>
              <input
                type="text"
                id="inputUsername"
                class="form-control"
                aria-describedby="passwordHelpBlock"
              />
              <label for="inputPassword" class="form-label">Password</label>
              <input
                type="text"
                id="inputPassword"
                class="form-control"
                aria-describedby="passwordHelpBlock"
              />
            </div>
            <button type="button" class="btn btn-outline-success">
              Dang Nhap
            </button>
          </div>
        </div>
        <p><span>or sign in with</span></p>
        <div class="row">
          <div class="col-6">
            <button
              type="button"
              class="btn btn-outline-danger"
              style="width: 200px"
            >
              Gmail
            </button>
          </div>
          <div class="col-6">
            <button
              type="button"
              class="btn btn-outline-info"
              style="width: 200px"
            >
              Facebook
            </button>
          </div>
        </div>
        <div class="modal-footer"></div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "BaseModal",
  props: {
    title: {
      type: String,
      required: true,
    },
  },
  methods: {
    onCloseModal() {
      this.$emit("cancel");
    },
  },
};
</script>

<style scoped>
.modal {
  display: block;
}

p {
  width: 100%;
  text-align: center;
  border-bottom: 1px dashed #000;
  line-height: 0.1em;
  margin: 10px 0 20px;
}

p span {
  background: #fff;
  padding: 0 10px;
}
</style>
