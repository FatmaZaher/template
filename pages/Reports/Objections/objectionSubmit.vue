<template>
  <div class="content subpage">
    <div class="text-center mt-4">
      <h5>{{ title }}</h5>
    </div>
    <b-form ref="form" @submit.stop.prevent="">
      <VSelectInput
        labelfor="reportNo"
        label="رقم التقرير"
        :options="reportNoList"
      />
      <b-row>
        <b-col cols="6">
          <VSelectInput
            labelfor="sampleNo"
            label="رقم العينة"
            :options="sampleNoList"
        /></b-col>
        <b-col cols="6" class="d-flex align-items-center w-100">
          <b-button class="btn main-btn w-100">
            <nuxt-link :to="'/NewSample'">
              <PlusIcon />
              <span class="ml-1"> {{ buttonTitle }}</span>
            </nuxt-link>
          </b-button>
        </b-col>
      </b-row>
      <FormFile
        labelfor="objectionFile"
        labelname="المرفقات"
        accept=".doc, .docx, .pdf"
      />
      <Textarea labelfor="objectionReson" labelname="سبب الإعتراض" />
      <div class="footer-button d-flex justify-content-center">
        <b-button type="submit" class="fot-btn main-btn w-100 mt-3"
          >إرسال</b-button
        >
      </div>
    </b-form>
  </div>
</template>
<script>
export default {
  data() {
    return {
      openmodal: false,
      buttonTitle: 'إضافة عينة جديدة',
      title: 'إضافة إعتراض',
      reportNoList: ['101', '212', '1212'],
      sampleNoList: ['01', '02', '03'],
    }
  },
}
</script>
<style scoped lang="scss"></style>
