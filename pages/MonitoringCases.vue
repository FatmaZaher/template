<template>
  <div class="page-content">
    <Header :title="title" />
    <div class="content">
      <div class="header-content">
        <b-row class="align-items-center">
          <b-col sm="12" md="6">
            <HeadPage :title="title"></HeadPage>
          </b-col>
          <b-col sm="12" md="6">
            <div>
              <b-button v-b-modal.add-modal class="btn">
                <i class="fas fa-plus"></i>
                <span>إضافة جديد </span>
              </b-button>
              <b-modal
                id="add-modal"
                ref="modal"
                title="إضافة حالة رصد"
                @show="resetModal"
                @hidden="resetModal"
                @ok="handleOk"
              >
                <form ref="form" @submit.stop.prevent="handleSubmit">
                  <b-row>
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
                    </b-col>
                  </b-row>

                  <div class="footer-button d-flex justify-content-center">
                    <b-button type="submit" class="fot-btn">إضافة</b-button>
                  </div>
                </form>
              </b-modal>
            </div>
          </b-col>
        </b-row>
      </div>
      <TableList
        :items="items"
        :rows="rows"
        :fields="fields"
        :is-edit="true"
        :is-delete="true"
      />
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      title: 'حالات الرصد',
      fields: [
        {
          key: 'sampleCode',
          label: 'رمز العينة',
        },
        {
          key: 'monitoringCase',
          label: 'حالة الرصد',
        },
        {
          key: 'id',
          label: '',
        },
      ],
      items: [
        {
          sampleCode: 'مثال',
          monitoringCase: 'خاطئة',
          id: 1,
        },
      ],
      sampleCode: '',
      monitoringCase: '',
      monitoringCases: ['صحيحة', 'خاطئة'],
    }
  },
  computed: {
    rows() {
      return this.items.length
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
</script>

<style></style>
