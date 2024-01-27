<template>
  <div class="footer">
    <div class="container">
      <div class="row">
        <div class="col">
          <div class="shop-name">
            <h3>NTV shop</h3>
          </div>
          <div class="contact-info">
            <div class="phone-number">
              <i class="bi bi-telephone p-1"> </i>
              <p class="p-1">sdt: 0968676702</p>
            </div>
            <div class="mail">
              <i class="bi bi-envelope p-1"></i>
              <p class="p-1">email: tranvu20032009@gmail.com</p>
            </div>
          </div>
        </div>
        <div class="col contact-section">
          <div class="contact-fb px-2">
            <i
              class="bi bi-facebook icon-fb-origin"
              style="font-size: 40px; color: white"
            ></i>
            <i
              class="bi bi-facebook icon-fb-mouse"
              style="font-size: 40px; color: #3887e0"
            ></i>
          </div>
          <div class="contact-ins px-2">
            <i
              class="bi bi-instagram icon-ins-origin"
              style="font-size: 40px; color: white"
            ></i>
            <i
              class="bi bi-instagram icon-ins-mouse"
              style="font-size: 40px; color: #f27cec"
            ></i>
          </div>
          <div class="contact-x px-2">
            <i
              class="bi bi-twitter-x icon-x-origin"
              style="font-size: 40px; color: white"
            ></i>
            <i
              class="bi bi-twitter-x icon-x-mouse"
              style="font-size: 40px; color: black"
            ></i>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>
<style lang="scss" scoped>
.footer {
  background-image: url(../assets/footer_image.png);
  object-fit: cover;
  margin-top: 20px;
  display: flex;
}
.contact-section {
  display: flex;
}
.icon-fb-mouse {
  display: none;
}
.contact-fb:hover {
  .icon-fb-origin {
    display: none;
  }
  .icon-fb-mouse {
    display: inline-block;
  }
}
.icon-ins-mouse {
  display: none;
}
.contact-ins:hover {
  .icon-ins-origin {
    display: none;
  }
  .icon-ins-mouse {
    display: inline-block;
  }
}
.icon-x-mouse {
  display: none;
}
.contact-x:hover {
  .icon-x-origin {
    display: none;
  }
  .icon-x-mouse {
    display: inline-block;
  }
}
.contact-info {
  color: white;
}

.phone-number {
  display: flex;
}
.mail {
  display: flex;
}
.shop-name {
  display: flex;
  color: white;
}
</style>
