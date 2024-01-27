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
          <div class="row">
            <div class="col-4">
              <img src="../assets/thankyou.jpg" class="img-fluid" />
            </div>
            <div class="col-8">
              <label for="inputPassword5" class="form-label">Username</label>
              <input
                type="text"
                id="inputUsername"
                class="form-control"
                aria-describedby="passwordHelpBlock"
              />
              <label for="inputAddress" class="form-label">Address</label>
              <input
                type="text"
                id="inputPassword5"
                class="form-control"
                aria-describedby="passwordHelpBlock"
              />
              <label for="inputPhoneNumber" class="form-label"
                >Phone Number</label
              >
              <input
                type="number"
                id="inputPassword5"
                class="form-control"
                aria-describedby="passwordHelpBlock"
              />
            </div>
          </div>

          <!-- <div class="card" style="width: 18rem">
            <img src="" class="card-img-top" alt="..." />
            <div class="card-body">
              <h5 class="card-title">Card title</h5>
              <p class="card-text">
                Some quick example text to build on the card title and make up
                the bulk of the card's content.
              </p>
              <a href="#" class="btn btn-primary">Go somewhere</a>
            </div>
          </div> -->
        </div>
        <div class="modal-footer">
          <button
            type="button"
            class="btn btn-secondary"
            data-bs-dismiss="modal"
            v-on:click="onCloseModal"
          >
            Close
          </button>
          <button type="button" class="btn btn-primary">Confirm Order</button>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "PlaceOrderModal",
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

<style></style>

<style scoped>
.modal {
  display: block;
}

.form-label {
  display: flex;
  text-align: left;
}
.img-fluid {
  display: flex;
  align-items: center;
}
</style>
