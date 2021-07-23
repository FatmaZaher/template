<template>
  <b-form-group
    :label="labelname"
    :label-for="labelfor"
  >
    <b-form-input
      :id="labelfor"
      :type="typeinput"
    ></b-form-input>
    
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
      },
      data() {
        return {
        }
      },
      computed: {
      },
    }
  </script>
  <style scoped lang="scss"></style>
</template>
