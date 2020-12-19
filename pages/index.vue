<template>
  <div class="main">
    <Header class="header-style" />
    <Container class="container-style" />
    <Footer class="footer-style" />
  </div>
</template>

<script>
export default {
  data() {
    return {}
  },
  head() {
    return {
      title: 'Navita',
      link: [
        {
          rel: 'icon',
          type: 'image/x-icon',
          href:
            'https://navita.com.br/wp-content/uploads/2018/06/navita-favicon.png',
        },
      ],
    }
  },
}
</script>
<style>
@import url('https://fonts.googleapis.com/css2?family=Lato:wght@100;300;400;700;900&display=swap');
body {
  font-family: 'Lato', sans-serif;
  margin: 0px;
}
.main {
  height: 100vh;
  display: flex;
  flex-direction: column;
}

/* .header-style {
} */
.container-style {
  flex: 3;
}
.footer-style {
  width: 100%;
}
</style>
