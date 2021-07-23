<template>
  <b-form-group :label="label" :label-for="labelfor">
    <v-select
      class="input"
      label="name"
      :options="options"
      :multiple="isMulti"
      dir="rtl"
    ></v-select>
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
