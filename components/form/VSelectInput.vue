<template>
  <b-form-group :label="label" :label-for="labelfor">
    <v-select
      class="input"
      label="name"
      :options="options"
      :multiple="isMulti"
      dir="rtl"
    ></v-select>
    <span class="inputIcon">
      <component :is="icon"></component>
    </span>
  </b-form-group>
</template>
<script>
export default {
  props: {
    value: {
      type: String,
      default: '',
    },
    label: {
      type: String,
      default: '',
    },
    labelfor: {
      type: String,
      default: '',
    },
    options: {
      type: Array,
      default: [],
    },
    isMulti: {
      type: Boolean,
      default: false,
    },
    icon: {
      type: String,
      default: 'PointIcon',
    },
  },
  computed: {
    select: {
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
<style scoped lang="scss">
</style>
