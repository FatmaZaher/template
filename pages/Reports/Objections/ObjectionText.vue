<template>
  <div>
    <Header
      :title="title"
      :subHeader="true"
      subHeaderlink="/Reports/Objections"
      :subHeaderTitle="subHeaderTitle"
    />
    <div class="content subpage">
      <div class="text-center mt-4">
        <h5>{{ title }}</h5>
      </div>
      <b-form ref="form" @submit.stop.prevent="">
        <Input
          labelfor="reportNo"
          labelname="رقم التقرير"
          typeinput="number"
          icon="ListIcon"
        />
        <Input
          labelfor="administration"
          labelname="الإدارة"
          typeinput="text"
          icon="AdminIcon"
        />
        <Textarea labelfor="objectionReson" labelname="سبب الإعتراض" />
      </b-form>
    </div>
  </div>
</template>
<script>
export default {
  data() {
    return {
      title: 'نص الإعتراض',
      subHeaderTitle: 'الإعتراضات',
      reportNoList: ['101', '212', '1212'],
      sampleNoList: ['01', '02', '03'],
    }
  },
  methods: {},
}
</script>
<style scoped lang="scss"></style>
