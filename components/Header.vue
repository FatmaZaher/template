<template>
  <div class="header">
    <b-row>
      <b-col cols="9" md="8" class="d-flex align-items-center">
        <img src="~/assets/images/logo.png" alt="logo" class="logo-img mr-md-3" />
        <nav aria-label="breadcrumb">
          <ol class="breadcrumb p-0 m-0">
            <li class="breadcrumb-item  mr-md-3">
              <nuxt-link :to="'/'">الرئيسية</nuxt-link>
            </li>
            <li
              v-if="subHeader"
              class="breadcrumb-item mr-md-3"
              style="fontsize: 16px !important"
            >
              <nuxt-link :to="subHeaderlink"
                ><PointIcon /><span class="ml-1">{{
                  subHeaderTitle
                }}</span></nuxt-link
              >
            </li>
            <li
              v-if="subHead"
              class="breadcrumb-item active"
              aria-current="page"
              style="fontsize: 15px !important"
            >
              <PointIcon />
              <span class="ml-1">{{ title }}</span>
            </li>
          </ol>
        </nav>
      </b-col>
      <b-col cols="3" md="4" class="d-flex justify-content-end">
        <nuxt-link :to="'/Profile'" class="mr-md-3 mr-1">
          <img
            src="~/assets/images/Photo.png"
            alt="personal picture"
            class="profiel-img"
          />
        </nuxt-link>
        <span class="language">EN</span>
      </b-col>
    </b-row>
  </div>
</template>
<script>
export default {
  props: {
    title: {
      type: String,
      default: '',
    },
    subHeader: {
      type: Boolean,
      default: false,
    },
    subHeaderlink: {
      type: String,
      default: '',
    },
    subHeaderTitle: {
      type: String,
      default: '',
    },
    subHead: {
      type: Boolean,
      default: true,
    },
    title: {
      type: String,
      default: '',
    },
  },
}
</script>
<style lang="scss"></style>
