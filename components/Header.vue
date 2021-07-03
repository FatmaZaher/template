<template>
  <div class="header">
    <b-row>
      <b-col sm="1">
        <div class="b-color"></div>
      </b-col>
      <div class="col-8 d-flex align-items-center">
        <nav aria-label="breadcrumb">
          <ol class="breadcrumb p-0 m-0">
            <li class="breadcrumb-item ml-4">
              <nuxt-link :to="'/'">الرئيسية</nuxt-link>
            </li>
            <li class="breadcrumb-item active" aria-current="page">{{title}}</li>
          </ol>
        </nav>
      </div>
      <div class="col-3">
        <span>EN</span>
        <nuxt-link :to="'/Profile'">
          <img src="~/assets/images/Photo.png" alt="" class="profiel-img"/>
        </nuxt-link>
      </div>
    </b-row>
  </div>
</template>
<script>
export default {
    props: ['title'],
}
</script>
<style lang="scss">
.profiel-img{
  cursor: pointer;
}
</style>
