<template>
  <div class="page-content">
    <Header :title="title"/>
    <div class="content subpage">
      <div class="text-center mt-4">
        <h6>{{title}}</h6>
      </div>
      <form ref="form" @submit.stop.prevent="handleSubmit">
        <b-form-group
          label="رقم التقرير"
          label-for="reportNo"
          invalid-feedback="Report No. is required"
        >
          <b-form-input
            id="reportNo"
            v-model="reportNo"
            required
          ></b-form-input>
        </b-form-group>
        <b-form-group
          label="رقم العينة"
          label-for="sampleNo"
          invalid-feedback="Sample Code is required"
        >
          <b-form-input
            id="sampleNo"
            v-model="sampleNo"
            required
          ></b-form-input>
        </b-form-group>

        <b-form-group label="المرفقات" label-for="file">
          <b-form-file
            id="file"
            placeholder="اختر المرفقات"
            drop-placeholder="Drop file here..."
          ></b-form-file>
        </b-form-group>
        <b-form-group
          label="التبرير"
          label-for="justification"
          invalid-feedback="Justification is required"
        >
          <b-form-textarea
            id="justification"
            v-model="justification"
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
  </div>
</template>

<script>
export default {
  data() {
    return {
      title: 'إضافة تبرير',
      reportNo: '',
      sampleNo: '',
      justification: '',
    }
  },
  methods: {
    checkFormValidity() {
      //const valid = this.$refs.form.checkValidity()
      //this.nameState = valid
      //return valid
    },
    resetModal() {
       /*(this.name = ''),
        (this.employeeNo = ''),
        (this.email = ''),
        (this.mobileNo = ''),
        (this.city = ''),
        (this.section = ''),
        (this.validity = ''),
        (this.administration = ''),
        (this.submittedNames = '')*/
    },
    handleOk(bvModalEvt) {
      // Prevent modal from closing
      //bvModalEvt.preventDefault()
      // Trigger submit handler
      //this.handleSubmit()
    },
    handleSubmit() {
      // Exit when the form isn't valid
      //if (!this.checkFormValidity()) {
      //  return
      //}
      // Push the name to submitted names
      //this.submittedNames.push(this.name)
      // Hide the modal manually
      //this.$nextTick(() => {
      //  this.$bvModal.hide('add-modal')
      //})
    },
  },
}
</script>
<style scoped lang="scss">
.subpage form {
  width: 400px;
  margin: 50px auto;
}
</style>
