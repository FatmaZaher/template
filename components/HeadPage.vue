<template>
  <div>
    <h6>{{ title }}</h6>
  </div>
</template>
<script>
export default {
  props: ['title'],
}
</script>
<style lang="scss">
@media (max-width: 767px) {
  h6 {
    font-size: 14px;
  }
}
</style>
