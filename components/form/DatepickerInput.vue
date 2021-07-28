<template>
  <b-form-group :label="labelname" :label-for="labelfor">
    <b-form-datepicker 
        :id="labelfor" 
        locale="ar" 
        calendar-width="100%">
    </b-form-datepicker>
  </b-form-group>
</template>
<script>
export default {
  props: {
    labelfor: {
      type: String,
      default: '',
    },
    labelname: {
      type: String,
      default: '',
    },
  },
}
</script>
<style scoped lang="scss"></style>
