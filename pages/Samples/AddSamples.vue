<template>
  <div>
    <Header
      :title="title"
      :subHeader="true"
      subHeaderlink="/Samples"
      :subHeaderTitle="subHeaderTitle"
    />
    <div class="content subpage">
      <div class="text-center mt-4">
        <h5>{{ title }}</h5>
      </div>
      <b-form ref="form" @submit.stop.prevent="">
        <Input
          labelfor="sampleCode"
          labelname="رمز العينة"
          typeinput="text"
          icon="CodesIcon"
        />
        <Input
          labelfor="sampleName"
          labelname="اسم العينة"
          typeinput="text"
          icon="FileCodeIcon"
        />
        <Input
          labelfor="samplesNo"
          labelname="عدد العينات"
          typeinput="number"
          icon="ListIcon"
        />
        <VSelectInput
          labelfor="administration"
          label="الإدارة"
          :options="administrationList"
          icon="AdminIcon"
        />
        <Input
          labelfor="responsible1"
          labelname="المسؤولية 1"
          typeinput="text"
          icon="FileCodeIcon"
        />
        <Input
          labelfor="responsible2"
          labelname="المسؤولية 2"
          typeinput="text"
          icon="FileCodeIcon"
        />
        <Input
          labelfor="responsible3"
          labelname="المسؤولية 3"
          typeinput="text"
          icon="FileCodeIcon"
        />
        <div class="footer-button d-flex justify-content-between">
          <b-button type="submit" class="fot-btn main-btn w-100 mt-3 mr-3"
            >حفظ</b-button
          >
          <b-button type="" class="fot-btn main-btn w-100 mt-3 close-btn"
            >إلغاء</b-button
          >
        </div>
      </b-form>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      title: 'إضافة عينة',
      subHeaderTitle: 'العينات',
      administrationList: [
        'إدارة التسويق',
        'الإدارة المالية',
        'إدارة الإنتاج',
        'إدارة التخطيط',
      ],
    }
  },
}
</script>
<style scoped lang="scss"></style>
