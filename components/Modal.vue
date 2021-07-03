<template>
  <b-modal
    id="add-modal"
    ref="modal"
    :title="title"
    @show="resetModal"
    @hidden="resetModal"
    @ok="handleOk"
  >
    <form ref="form" @submit.stop.prevent="handleSubmit">
      <b-row>
        <b-col sm="12" md="6" v-if="isEmployeeNo">
          <b-form-group
            label="رقم الموظف"
            label-for="employeeNo"
            invalid-feedback="Employee No. is required"
          >
            <b-form-input
              id="employeeNo"
              v-model="employeeNo"
              required
            ></b-form-input>
          </b-form-group>
        </b-col>
        <b-col sm="12" md="6" v-if="isEmployeeName">
          <b-form-group
            label="الإسم"
            label-for="employeeName"
            invalid-feedback="Name is required"
          >
            <b-form-input
              id="employeeName"
              v-model="employeeName"
              required
            ></b-form-input>
          </b-form-group>
        </b-col>
      </b-row>

      <div class="footer-button d-flex justify-content-center">
        <b-button type="submit" class="fot-btn">حفظ</b-button>
      </div>
    </form>
  </b-modal>
</template>

<script>
export default {
  data() {
    return {
      employeeNo: '',
      employeeName: '',
    }
  },
  props: {
    title: {
      type: null,
      default: ''
    },
    isEmployeeNo: {
      type: Boolean,
      default: false,
    },
    isEmployeeName: {
      type: Boolean,
      default: false,
    },
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