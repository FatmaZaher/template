<template>
  <div class="page-content">
    <Header :title="title" />
    <div class="content subpage">
      <div class="text-center mt-4">
        <h6>{{ title }}</h6>
      </div>
      <form ref="form" @submit.stop.prevent="handleSubmit">
        <b-form-group
          label="حالة الرصد"
          label-for="monitoringCase"
          invalid-feedback="Monitoring Case Case is required"
        >
          <b-form-select
            id="monitoringCase" 
            :options="monitoringCases"
            v-model="monitoringCase"
           ></b-form-select>
        </b-form-group>
        <b-form-group
          label="ملاحظات إدارة الجودة"
          label-for="notice"
          invalid-feedback="notice is required"
        >
          <b-form-textarea
            id="notice"
            v-model="notice"
            placeholder=""
            rows="2"
            required
          ></b-form-textarea>
        </b-form-group>
        <b-form-group
          label="تاريخ الإجراء التصحيحي"
          label-for="correciveDate"
          invalid-feedback="Date is required"
        >
          <b-form-datepicker id="correciveDate" v-model="correciveDate">
          </b-form-datepicker>
        </b-form-group>

        <div class="footer-button d-flex justify-content-between">
          <b-button type="submit" class="fot-btn w-100 mt-3">تحقق</b-button>
        </div>
      </form>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      title: 'عملية الرصد',
      monitoringCase: '',
      monitoringCases: ['صحيحة', 'خاطئة'],
      notice: '',
      correciveDate: '',
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
