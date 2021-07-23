<template>
  <div class="header">
    <b-row>
      <b-col cols="0" sm="1">
        <div class="b-color"></div>
      </b-col>
      <b-col cols="6" sm="6" class="d-flex align-items-center">
        <nav aria-label="breadcrumb">
          <ol class="breadcrumb p-0 m-0">
            <li class="breadcrumb-item mr-4">
              <nuxt-link :to="'/'">الرئيسية</nuxt-link>
            </li>
            <li class="breadcrumb-item active" aria-current="page">الفرع</li>
          </ol>
        </nav>
      </b-col>
      <b-col cols="6" sm="5">
        <span>EN</span>
        <nuxt-link :to="'/Profile'">
          <img src="~/assets/images/Photo.png" alt="personal picture" class="profiel-img"/>
        </nuxt-link>
      </b-col>
    </b-row>
  </div>
</template>
<script>
export default {
}
</script>
<style lang="scss">
.profiel-img{
  cursor: pointer;
}
</style>
