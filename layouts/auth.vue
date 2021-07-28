<template>
  <nuxt />
</template>
<script>
export default {
  head: {
    titleTemplate: 'Quality-login',
  },
    mounted() {
    document.querySelector('html').setAttribute('dir', 'rtl')
  },
}
</script>
<style>
@import url('https://fonts.googleapis.com/css2?family=Almarai:wght@300;400;700;800&display=swap');
@import url('https://cdnjs.cloudflare.com/ajax/libs/font-awesome/5.15.3/css/all.min.css');
@import url('~/assets/scss/style.scss');

</style>
