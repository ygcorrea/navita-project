<template>
  <div>
    <div class="footer-content">
      {{ footerText }} <span>&copy;</span> {{ mainText }}
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      footerText: 'Copyrigth',
      mainText: ' Navita 2020',
    }
  },
}
</script>
<style>
.footer-content {
  background: #ffff;
  display: flex;
  align-items: center;
  justify-content: center;
  height: 50px;
}
</style>
