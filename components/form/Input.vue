<template>
  <b-form-group :label="labelname" :label-for="labelfor">
    <b-form-input :id="labelfor" :type="typeinput"></b-form-input>
    <span class="inputIcon">
      <component :is="icon"></component>
    </span>
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
    typeinput: {
      type: String,
      default: '',
    },
    icon: {
      type: String,
      default: 'PointIcon',
    },
  },
  data() {
    return {}
  },
  computed: {},
}
</script>
<style scoped lang="scss">
span {
  position: absolute;
  right: 30px;
  top: 37px;
}
</style>
