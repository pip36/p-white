<template>
  <section class="container">
    <div>
      <h1 class="title">
        Phil White
      </h1>
      <h2 class="subtitle">
        portfolio
      </h2>
      <div class="links">
        <nuxt-link to="/" class="button--grey"> Home </nuxt-link>
        <a
          href="https://github.com/pip36"
          target="_blank"
          class="button--grey">GitHub <i class="fab fa-github"></i> </a>
        <nuxt-link to="/about" class="button--grey"> About </nuxt-link>
      </div>

      <p>
          all about me
      </p>
    </div>
  </section>
</template>

<script>

export default {
 
}
</script>

<style scoped>
.container {
  min-height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
  text-align: center;
}

.title {
  font-family: "Quicksand", "Source Sans Pro", -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, "Helvetica Neue", Arial, sans-serif; /* 1 */
  display: block;
  font-weight: 300;
  font-size: 100px;
  color: #35495e;
  letter-spacing: 1px;
}

.subtitle {
  font-weight: 300;
  font-size: 42px;
  color: #526488;
  word-spacing: 5px;
  padding-bottom: 15px;
}

.links {
  padding-top: 15px;
}

@media screen and ( max-width: 760px ){ 
  .title {
    font-size: 50px;
  }
  .subtitle {
    font-size: 30px;
  }
}
</style>
