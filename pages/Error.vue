<template>
  <div class="content">
    <div class="d-flex mb-5">
      <img src="~/assets/images/error.webp" alt="error" class="w-50 m-auto" />
    </div>
    <p class="text-center my-5">الصفحة المطلوبة غير موجودة</p>
    <div class="text-center my-5">
      <b-button class="btn main-btn">
        <nuxt-link :to="'/'">
          الرجوع للرئيسية
        </nuxt-link>
      </b-button>
    </div>
  </div>
</template>

<script>
export default {}
</script>
<style scoped lang="scss"></style>
