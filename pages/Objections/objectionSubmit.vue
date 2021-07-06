<template>
  <div class="content subpage">
    <div class="text-center mt-4">
      <h6>{{ title }}</h6>
    </div>
    <form ref="form" @submit.stop.prevent="">
      <b-form-group
        label="رقم التقرير"
        label-for="reportNo"
        invalid-feedback="Report No. is required"
      >
        <b-form-input id="reportNo" v-model="reportNo" required></b-form-input>
      </b-form-group>
      <b-form-group
        label="رقم العينة"
        label-for="sampleNo"
        invalid-feedback="Sample NO. is required"
      >
        <b-form-input id="sampleNo" v-model="sampleNo" required></b-form-input>
      </b-form-group>

      <b-form-group label="المرفقات" label-for="file">
        <b-form-file
          id="file"
          placeholder="اختر المرفقات"
          drop-placeholder="Drop file here..."
        ></b-form-file>
      </b-form-group>
      <b-form-group
        label="سبب الإعتراض"
        label-for="objectionReson"
        invalid-feedback="Objection Reson is required"
      >
        <b-form-textarea
          id="objectionReson"
          v-model="objectionReson"
          placeholder="اشرح السبب هنا ....."
          rows="3"
          required
        ></b-form-textarea>
      </b-form-group>
      <div class="footer-button d-flex justify-content-center">
        <b-button type="submit" class="fot-btn w-100 mt-3">إرسال</b-button>
      </div>
    </form>
  </div>
</template>

<script>
export default {
  data() {
    return {
      title: 'إضافة إعتراض',
      reportNo: '',
      sampleNo: '',
      objectionReson: '',
    }
  },
}
</script>
<style scoped lang="scss">
</style>
