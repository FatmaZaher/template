<template>
  <div class="content subpage">
    <div class="text-center mt-4">
      <h5>{{ title }}</h5>
    </div>
    <b-form ref="form" @submit.stop.prevent="">
      <VSelectInput
        labelfor="monitoringCase"
        label="حالة الرصد"
        :options="monitoringCaseList"
      />
      <Textarea labelfor="notice" labelname="ملاحظات إدارة الجودة" />
      <DatepickerInput
        labelfor="correciveDate"
        labelname="تاريخ الإجراء التصحيحي"
      />
      <div class="footer-button d-flex justify-content-between">
        <b-button type="submit" class="fot-btn main-btn w-100 mt-3"
          >تحقق</b-button
        >
      </div>
    </b-form>
  </div>
</template>

<script>
export default {
  data() {
    return {
      title: 'عملية الرصد',
      monitoringCaseList: ['صحيحة', 'خاطئة'],
    }
  },
}
</script>
<style scoped lang="scss"></style>
