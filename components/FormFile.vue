<template>
  <b-form-group :label="labelname" :label-for="labelfor">
    <b-form-file
      :id="labelfor"
      placeholder=""
      drop-placeholder="Drop file here..."
    ></b-form-file>
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
<style scoped lang="scss"></style>
