<template>
  <div class="content subpage">
    <div class="text-center mt-4">
      <h5>{{ title }}</h5>
    </div>
    <b-form ref="form" @submit.stop.prevent="">
      <Input labelfor="reportNo" labelname="رقم التقرير" typeinput="number" />
      <Input labelfor="administration" labelname="الإدارة" typeinput="text" />
      <Textarea labelfor="objectionReson" labelname="سبب الإعتراض" />
    </b-form>

  </div>
</template>
<script>
export default {
  data() {
    return {
      title: 'نص الإعتراض',
      reportNoList: ['101', '212', '1212'],
      sampleNoList: ['01', '02', '03'],
    }
  },
  methods: {}
}
</script>
<style scoped lang="scss"></style>
