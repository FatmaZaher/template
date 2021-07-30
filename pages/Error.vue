<template>
  <div class="error">
    <div class="p-5 text-center">
      <ErrorSvg />
    </div>
    <p class="text-center my-3">الصفحة المطلوبة غير موجودة</p>
    <div class="text-center my-5">
      <b-button class="btn main-btn">
        <nuxt-link :to="'/'"> الرجوع للرئيسية </nuxt-link>
      </b-button>
    </div>
  </div>
</template>

<script>
export default {
  layout: 'auth',
}
</script>
<style scoped lang="scss">
.error {
  svg {
    width: 50%;
  }
  @media (max-width: 767px) {
    padding: 120px 0;
    svg {
      width: 100%;
    }
  }
}
</style>
