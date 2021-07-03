<template>
  <div class="page-content">
    <Header :title="title" />
    <div class="content subpage">
      <div class="text-center mt-4">
        <h6>{{ title }}</h6>
        <p>يرجى إدخال جميع بيانات التحقق</p>
      </div>
      <form ref="form" @submit.stop.prevent="handleSubmit">
        <b-row>
          <b-col sm="12" md="6">
            <b-form-group
              label="حالة التحقق"
              label-for="verificationCase"
              invalid-feedback="Verification Case is required"
            >
              <b-form-select
                id="verificationCase"
                v-model="verificationCase"
                :options="verificationCases"
                required
              ></b-form-select>
            </b-form-group>
          </b-col>

          <b-col sm="12" md="6">
            <b-form-group
              label="رمز العينة"
              label-for="sampleCode"
              invalid-feedback="Sample Code is required"
            >
              <b-form-input
                id="sampleCode"
                v-model="sampleCode"
                required
              ></b-form-input>
            </b-form-group>
          </b-col>

          <b-col sm="12" md="6">
            <b-form-group
              label="اسم العينة"
              label-for="sampleName"
              invalid-feedback="Sample Name Code is required"
            >
              <b-form-input
                id="sampleName"
                v-model="sampleName"
                required
              ></b-form-input>
            </b-form-group>
          </b-col>

          <b-col sm="12" md="6">
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
          </b-col>
          <b-col sm="12">
            <div class="footer-button d-flex justify-content-between">
              <b-button v-b-modal.add-modal class="fot-btn w-100 mt-3 ml-3">
                <i class="fas fa-plus"></i>
                <span>إضافة عينة جديدة </span>
              </b-button>

              <b-button v-b-modal.add-modal class="fot-btn w-100 mt-3">
                <i class="fas fa-cog"></i>
                <span>المقارنة والتحقق</span>
              </b-button>
            </div>
          </b-col>
        </b-row>
      </form>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      title: 'عملية التحقق',
      sampleCode: '',
      sampleName: '',
      sampleNo: '',
      verificationCase: '',
      verificationCases: ['لم يتم التحقق بعد', 'جاري التحقق', 'تم التحقق'],
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
