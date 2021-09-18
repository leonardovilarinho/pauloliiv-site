<template>
  <main>
    <section class="grid banner" data-grid="center-center">
      <img src="~/assets/images/logo.png"/>
    </section>

    <section class="grid" data-grid="column">
      <h2 class="subtitle">Latest single</h2>
      <posts post-type="feature" :amount="1" />
    </section>
  </main>
</template>

<style lang="css" scoped>
.banner {
  height: calc(100vh - 100px);
}

.banner img {
  width: 60%;
}

.subtitle {
  color: #fff;
  margin-bottom: 30px;
  text-align: center;
}
</style>