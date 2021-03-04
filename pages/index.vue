<template>
  <div>
    <div class="header">
      <Logo />
      <h1 class="title">livros</h1>
    </div>
    <div class="contest">
      {{ info }}
    </div>
  </div>
</template>

<script>
import axios from 'axios'

export default {
  data() {
    return {
      info: null,
    }
  },
  mounted() {
    axios
      .get(
        'https://www.googleapis.com/books/v1/volumes?q=evolution+inauthor:darwin&key=suaChaveDaAPI'
      )
      .then((response) => (this.info = response))
  },
}
</script>

<style>
.header {
  text-align: center;
  width: 50%;
}

.title {
  font-family: 'Quicksand', 'Source Sans Pro', -apple-system, BlinkMacSystemFont,
    'Segoe UI', Roboto, 'Helvetica Neue', Arial, sans-serif;
  display: block;
  font-weight: 300;
  font-size: 30px;
  color: #35495e;
  letter-spacing: 1px;
}
</style>
