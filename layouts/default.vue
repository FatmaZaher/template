<template>
  <div class="">
    <b-container fluid>
      <SideBar />
      <nuxt />
    </b-container>
  </div>
</template>
<script>
export default {
  head: {
    titleTemplate: 'Quality',
  },
}
</script>
<style>

@import url('https://fonts.googleapis.com/css2?family=Tajawal:wght@300;500;700;800&display=swap');
@import url('https://cdnjs.cloudflare.com/ajax/libs/font-awesome/5.15.3/css/all.min.css');
@import url('~/assets/scss/style.scss');

html {
  -webkit-text-size-adjust: 100%;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  direction: rtl;
}
body {
  margin: 0;
  font-family: 'Tajawal', sans-serif;
  font-size: 14px;
  line-height: 1.5;
  text-align: right;
  color: var(--text-color);
}
h1,
h2,
h3,
h4,
h5,
h6,
.h1,
.h2,
.h3,
.h4,
.h5,
.h6 {
  font-weight: 600;
}
</style>
