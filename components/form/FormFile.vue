<template>
  <b-form-group :label="labelname" :label-for="labelfor">
    <b-form-file
      v-model="text"
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
    value: {
      type: String,
      default: '',
    },
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
  computed: {
    text: {
      get() {
        return this.value
      },
      set(value) {
        this.$emit('input', value)
      },
    },
  },
}
</script>
<style scoped lang="scss"></style>
