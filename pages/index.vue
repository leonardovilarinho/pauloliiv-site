<template>
  <main>
    <div class="background-cover"></div>
    <section class="grid banner" data-grid="center-center">
      <img src="~/assets/images/logo.png"/>
    </section>

    <!-- <img class="background-cover" src="~/assets/images/cover-back.jpg"/> -->

    <section id="home" class="grid section" data-grid="column">
      <h2 class="subtitle">Latest singl<span style="color:#fff200">e</span></h2>
      <posts post-type="feature" :amount="1" />
    </section>

    <section id="media" class="grid section" data-grid="column">
      <h2 class="subtitle">Musi<span style="color:#fff200">c</span></h2>
      <posts post-type="projects" :amount="99" />
    </section>

    <footer id="contact" class="footer section grid">
      <img class="grid" src="~/assets/images/logo-square.png" alt="Paul Oliiv">

      <a  class="grid" href="mailto:me@pauloliiv.com">me@pauloliiv.com</a>

      <div class="grid links">
        <p class="grid">Follow me:</p>
        <ul class="col-6 grid list--horizontal list--unstyled">
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

        <small class="grid">© {{ (new Date()).getFullYear()}} - Paul Oliiv</small>
      </div>
    </footer>
  </main>
</template>

<style lang="css" scoped>

.footer {
  justify-content: center;
  align-items: center;
}

.footer .link {
  font-size: 20px;
  padding: 10px;
}

.footer .links {
  height: fit-content;
}

.footer .links > * {
  margin: 10px 0px;
}

.footer img {
  height: 180px;
  width: auto;
}
.footer * {
  color: #fff;
  justify-content: center;
  align-items: center;
  margin: 0px;
  padding: 0px;
}
.banner:after {
  width: 100%;
  height: 100vh;
  background-image: url('~/assets/images/cover-back.jpg');
  background-size: 100% auto;
  background-position-y: -100px;
  background-repeat: no-repeat;
  position: absolute;
  content: '';
  z-index: 1;
  opacity: 0.2;
}

.section {
  min-height: 100vh;
  justify-content: center;
}

.banner {
  z-index: 100;
  height: calc(100vh - 100px);
  background: transparent;
}

.background-cover {
  position: absolute;
  top: 0px;
}

.banner img {
  z-index: 100;
  width: 60%;
  opacity: 1;
}

.subtitle {
  color: #fff;
  margin: 00px 0px 70px;
  text-align: center;
}

#media:after {
  width: 100%;
  height: 100vh;
  background-image: url('~/assets/images/background.jpg');
  background-size: 100% auto;
  background-repeat: no-repeat;
  position: absolute;
  content: '';
  z-index: 1;
  opacity: 0.4;
}

#media * {
  z-index: 2;
}

@media screen and (max-width: 1024px) {
  .banner img {
    width: 95%;
  }
  .banner:after {
    background-size: auto 100%;
    background-position-y: -60px;
  }

  #media:after {
    background-size: auto 100%;
    background-position: -160px;
  }
}
</style>