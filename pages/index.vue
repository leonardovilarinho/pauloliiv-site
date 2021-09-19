<template>
  <main>
    <div class="background-cover"></div>
    <section class="grid banner" data-grid="center-center">
      <img src="~/assets/images/logo.png"/>
    </section>

    <!-- <img class="background-cover" src="~/assets/images/cover-back.jpg"/> -->

    <section id="home" class="grid" data-grid="column">
      <h2 class="subtitle">Latest single</h2>
      <posts post-type="feature" :amount="1" />
    </section>

    <section id="media" class="grid" data-grid="column">
      <h2 class="subtitle">Music</h2>
      <posts post-type="projects" :amount="99" />
    </section>
  </main>
</template>

<style lang="css" scoped>
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
  margin-bottom: 30px;
  text-align: center;
}
</style>