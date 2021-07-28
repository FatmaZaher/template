<template>
  <b-form-group :label="labelname" :label-for="labelfor">
    <b-form-textarea
      :id="labelfor"
      placeholder=""
    ></b-form-textarea>
  </b-form-group>
</template>
<script>
export default {
  props: {
    labelname: {
      type: String,
      default: '',
    },
    labelfor: {
      type: String,
      default: '',
    },
  },
}
</script>
<style scoped lang="scss">
.form-group .form-control {
  min-height: 120px !important;
}

</style>
