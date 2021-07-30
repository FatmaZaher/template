<template>
  <div>
    <Header :title="title" />
    <div class="content subpage">
      <div class="text-center mt-4">
        <h5>{{ title }}</h5>
      </div>
      <b-form ref="form" @submit.stop.prevent="">
        <VSelectInput
          labelfor="reportNo"
          label="رقم التقرير"
          :options="reportNoList"
          icon="ListIcon"
        />
        <b-row>
          <b-col cols="6">
            <VSelectInput
              labelfor="sampleNo"
              label="رقم العينة"
              :options="sampleNoList"
              icon="ListIcon"
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
          labelfor="justificationFile"
          labelname="اختر المرفقات"
          accept=".doc, .docx, .pdf"
        />
        <Textarea labelfor="justification" labelname="التبرير" />
        <div class="footer-button d-flex justify-content-center">
          <b-button type="submit" class="fot-btn main-btn w-100 mt-3"
            >إرسال</b-button
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
      buttonTitle: 'إضافة عينة جديدة',
      title: 'إضافة تبرير',
      reportNoList: ['101', '212', '1212'],
      sampleNoList: ['01', '02', '03'],
    }
  },
}
</script>
<style scoped lang="scss"></style>
