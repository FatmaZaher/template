<template>
  <div class="text-left">
    <h6 class="title">{{ title }}</h6>
  </div>
</template>
<script>
export default {
  props: ['title'],
}
</script>
<style lang="scss">
.title{
  font-size: 18px;
  font-weight: 700;
}
@media (max-width: 767px) {
 .title {
    font-size: 15px;
  }
}
</style>
