<template>
  <div>
    <p class="header-title">{{ headerText }}</p>
  </div>
</template>

<script>
export default {
  data() {
    return {
      headerText: 'Navita',
    }
  },
}
</script>

<style>
.header-title {
  color: #1cc88a;
  font-size: 1.1em;
  margin-left: 35px;
  font-weight: bold;
}
</style>
