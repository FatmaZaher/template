<template>
  <b-form-group :label="labelname" :label-for="labelfor">
    <b-form-file
      :id="labelfor"
      placeholder=""
      drop-placeholder="أسقط الملف هنا..."
      :accept="accept"
      :multiple="isMulti"
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
    isMulti: {
      type: Boolean,
      default: false,
    },
    accept: {
      type: null,
      default: '',
    },
  },

}
</script>
<style scoped lang="scss"></style>
