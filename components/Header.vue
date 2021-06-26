<template>
  <div class="header">
    <div class="row">
      <div class="col-1">
        <div class="b-color"></div>
      </div>
      <div class="col-8 d-flex align-items-center">
        <nav aria-label="breadcrumb">
          <ol class="breadcrumb p-0 m-0">
            <li class="breadcrumb-item ml-4"><nuxt-link :to="'/home'">الرئيسية</nuxt-link></li>
            <li class="breadcrumb-item active" aria-current="page">الفرع</li>
          </ol>
        </nav>
      </div>
      <div class="col-3">
        <span>EN</span>
        <img src="~/assets/images/Photo.png" alt="" />
      </div>
    </div>
  </div>
</template>
<script>
</script>
<style lang="scss">

</style>
