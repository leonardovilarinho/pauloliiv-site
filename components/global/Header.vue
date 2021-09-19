<template>
  <nav class="header grid" aria-label="Main Menu">
    <ul class="col-6 grid list--horizontal list--unstyled">
      <li class="col link">
        <a href="#home">
          <img src="~/assets/images/logo-square.png"/>
          HOME
        </a>
      </li>

      <li class="col link">
        <a href="#media">
          <img src="~/assets/images/logo-square.png"/>
          MEDIA
        </a>
      </li>

      <!-- <li class="col link">
        <a href="#about">
          <img src="~/assets/images/logo-square.png"/>
          ABOUT
        </a>
      </li> -->

      <li class="col link">
        <a href="#contact">
          <img src="~/assets/images/logo-square.png"/>
          CONTACT
        </a>
      </li>
    </ul>

    <ul class="links col-6 grid list--horizontal list--unstyled">
      <li class="col link">
        <a href="#home">
          <i class="fab fa-facebook-f"></i>
        </a>
      </li>

      <li class="col link">
        <a href="#home">
          <i class="fab fa-twitter"></i>
        </a>
      </li>

      <li class="col link">
        <a href="#home">
          <i class="fab fa-instagram"></i>
        </a>
      </li>

      <li class="col link">
        <a href="#home">
          <i class="fab fa-tiktok"></i>
        </a>
      </li>

      <li class="col link">
        <a href="#home">
          <i class="fab fa-soundcloud"></i>
        </a>
      </li>

      <li class="col link">
        <a href="#home">
          <i class="fab fa-spotify"></i>
        </a>
      </li>

      <li class="col link">
        <a href="#home">
          <i class="fab fa-deezer"></i>
        </a>
      </li>

      <li class="col link">
        <a href="#home">
          <i class="fab fa-youtube"></i>
        </a>
      </li>
    </ul>
  </nav>
</template>

<script>
export default {
  name: 'Header'
}
</script>

<style lang="css" scoped>
.header {
  padding: 20px 0px 30px;
  align-items: center;
  justify-content: space-around;
}

.header > .grid {
  justify-content: center;
  align-items: center;
}

.link {
  padding: 0px 10px;
}

.link > * {
  display: flex;
  flex-flow: column;
  justify-content: center;
  align-items: center;
  color: #fafafa;
  font-size: 15px;
}

.link img {
  height: 40px;
}

.link .fab {
  font-size: 20px;
}

@media screen and (max-width: 1024px) {
  .links {
    margin-top: 20px;
  }
}
</style>
