<template>
  <div>
    <Header
      :title="title"
      :subHeader="true"
      subHeaderlink="/Action"
      :subHeaderTitle="subHeaderTitle"
    />
    <div class="content subpage">
      <div class="text-center mt-4">
        <h5>{{ title }}</h5>
      </div>
      <b-form ref="form" @submit.stop.prevent="">
        <Input
          labelfor="actionNo"
          labelname="رقم الإجراء"
          typeinput="number"
          icon="ListIcon"
        />
        <Input
          labelfor="administration"
          labelname="الإدارة"
          typeinput="text"
          icon="AdminIcon"
        />
        <Textarea labelfor="actionText" labelname="نص الإجراء" />
      </b-form>
    </div>
  </div>
</template>
<script>
export default {
  data() {
    return {
      title: 'نص الإجراء',
      subHeaderTitle: 'الإجراءات',
      reportNoList: ['101', '212', '1212'],
      sampleNoList: ['01', '02', '03'],
    }
  },
  methods: {},
}
</script>
<style scoped lang="scss"></style>
