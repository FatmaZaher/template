<template>
  <div class="header-content">
    <div class="row align-items-center">
      <div class="col-6">
        <h6>اسم القسم (مثل الموظفين)</h6>
      </div>
      <div class="col-6">
        <div>
          <b-button v-b-modal.add-employee class="btn">
            <i class="fas fa-plus"></i>
            <span>إضافة موظف </span>
          </b-button>

          <b-modal
            id="add-employee"
            ref="modal"
            title="إضافة موظف"
            @show="resetModal"
            @hidden="resetModal"
            @ok="handleOk"
          >
            <form ref="form" @submit.stop.prevent="handleSubmit">
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

              <b-form-group
                label="الإسم"
                label-for="name"
                invalid-feedback="Name is required"
              >
                <b-form-input id="name" v-model="name" required></b-form-input>
              </b-form-group>

              <b-form-group
                label="البريد الإلكتروني"
                label-for="email"
                invalid-feedback="Email is required"
              >
                <b-form-input
                  id="email"
                  v-model="email"
                  :state="nameState"
                  required
                ></b-form-input>
              </b-form-group>

              <b-form-group
                label="رقم الهاتف"
                label-for="mobileNo"
                invalid-feedback="Mobile No. is required"
              >
                <b-form-input
                  id="mobileNo"
                  v-model="mobileNo"
                  required
                ></b-form-input>
              </b-form-group>

              <b-form-group
                label="المدينة"
                label-for="city"
                invalid-feedback="City is required"
              >
                <b-form-select
                  id="city"
                  v-model="city"
                  :options="cites"
                  required
                ></b-form-select>
              </b-form-group>

              <b-form-group
                label="الصلاحية"
                label-for="validity"
                invalid-feedback="Validity is required"
              >
                <b-form-select
                  id="validity"
                  v-model="validity"
                  :options="validites"
                  required
                ></b-form-select>
              </b-form-group>

              <b-form-group
                label="القسم"
                label-for="section"
                invalid-feedback="Section is required"
              >
                <b-form-select
                  id="section"
                  v-model="section"
                  :options="sections"
                  required
                ></b-form-select>
              </b-form-group>

              <b-form-group
                label="الإدارة"
                label-for="administration"
                invalid-feedback="Administration is required"
              >
                <b-form-select
                  id="administration"
                  v-model="administration"
                  :options="administrations"
                  required
                ></b-form-select>
              </b-form-group>

              <b-form-file
                v-model="file1"
                placeholder="إضافة صورة"
                drop-placeholder="Drop file here..."
              ></b-form-file>
              <div class="footer-button d-flex justify-content-center">
                <b-button type="submit" class="fot-btn">حفظ</b-button>
              </div>
            </form>
          </b-modal>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      employeeNo: '',
      name: '',
      email: '',
      mobileNo: '',
      city: '',
      section: '',
      validity: '',
      administration: '',
      submittedNames: '',
      validites: ['validity', 'validity', 'validity', 'validity'],
      cites: ['city 1', 'city 1', 'city 1', 'city 1', 'city 1', 'city 1'],
      sections: ['section 1', 'section 1', 'section 1', 'section 1'],
      administrations: [
        'administration',
        'administration',
        'administration',
        'administration',
      ],
    }
  },
  methods: {
    checkFormValidity() {
      //const valid = this.$refs.form.checkValidity()
      //this.nameState = valid
      //return valid
    },
    resetModal() {
      ;(this.name = ''),
        (this.employeeNo = ''),
        (this.email = ''),
        (this.mobileNo = ''),
        (this.city = ''),
        (this.section = ''),
        (this.validity = ''),
        (this.administration = ''),
        (this.submittedNames = '')
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
      //  this.$bvModal.hide('add-employee')
      //})
    },
  },
}
</script>
<style lang="scss">

</style>
