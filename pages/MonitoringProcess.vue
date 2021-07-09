<template>
  <div class="content subpage">
    <div class="text-center mt-4">
      <h6>{{ title }}</h6>
    </div>
    <form ref="form" @submit.stop.prevent="">
      <b-form-group
        label="حالة الرصد"
        label-for="monitoringCase"
        invalid-feedback="Monitoring Case Case is required"
      >
        <v-select dir="ltr" :options="monitoringCases"></v-select>
      </b-form-group>
      <b-form-group
        label="ملاحظات إدارة الجودة"
        label-for="notice"
        invalid-feedback="notice is required"
      >
        <b-form-textarea id="notice" rows="2" required></b-form-textarea>
      </b-form-group>
      <b-form-group
        label="تاريخ الإجراء التصحيحي"
        label-for="correciveDate"
        invalid-feedback="Date is required"
      >
        <b-form-datepicker id="correciveDate"> </b-form-datepicker>
      </b-form-group>
      <div class="footer-button d-flex justify-content-between">
        <b-button type="submit" class="fot-btn w-100 mt-3">تحقق</b-button>
      </div>
    </form>
  </div>
</template>

<script>
export default {
  data() {
    return {
      title: 'عملية الرصد',
      monitoringCases: ['صحيحة', 'خاطئة'],
    }
  },
}
</script>
<style scoped lang="scss">
</style>
