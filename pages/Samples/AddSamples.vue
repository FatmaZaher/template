<template>
  <div class="content subpage">
    <div class="text-center mt-4">
      <h5>{{ title }}</h5>
    </div>
    <b-form ref="form" @submit.stop.prevent="">
      <Input labelfor="sampleCode" labelname="رمز العينة" typeinput="text" />
      <Input labelfor="sampleName" labelname="اسم العينة" typeinput="text" />
      <Input labelfor="samplesNo" labelname="عدد العينات" typeinput="number" />
      <VSelectInput
        labelfor="administration"
        label="الإدارة"
        :options="administrationList"
      />
      <Input labelfor="responsible1" labelname="المسؤولية 1" typeinput="text" />
      <Input labelfor="responsible2" labelname="المسؤولية 2" typeinput="text" />
      <Input labelfor="responsible3" labelname="المسؤولية 3" typeinput="text" />
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
</template>

<script>
export default {
  data() {
    return {
      title: 'إضافة عينة',
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
