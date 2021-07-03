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
                <span>إضافة تقرير قيد التحقق </span>
              </b-button>

              <b-modal
                id="add-modal"
                ref="modal"
                title="إضافة تقرير قيد التحقق"
                @show="resetModal"
                @hidden="resetModal"
                @ok="handleOk"
              >
                <form ref="form" @submit.stop.prevent="handleSubmit">
                  <b-row>
                    <b-col sm="12" md="6">
                      <b-form-group
                        label="رمز التقرير"
                        label-for="reportCode"
                        invalid-feedback="Report Code is required"
                      >
                        <b-form-input
                          id="reportCode"
                          v-model="reportCode"
                          required
                        ></b-form-input>
                      </b-form-group>
                    </b-col>
                    <b-col sm="12" md="6">
                      <b-form-group
                        label="رموز الحالات"
                        label-for="casesCodes"
                        invalid-feedback="Cases Code is required"
                      >
                        <b-form-input
                          id="casesCodes"
                          v-model="casesCodes"
                          required
                        ></b-form-input>
                      </b-form-group>
                    </b-col>
                    <b-col sm="12" md="6">
                      <b-form-group
                        label="تاريخ الإصدار"
                        label-for="releaseDate"
                        invalid-feedback="Date is required"
                      >
                        <b-form-datepicker
                          id="releaseDate"
                          v-model="releaseDate"
                        >
                        </b-form-datepicker>
                      </b-form-group>
                    </b-col>
                    <b-col sm="12" md="6">
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
                    </b-col>
                    <b-col sm="12" md="6">
                      <b-form-group
                        label="مصدر الرصد"
                        label-for="monitoringSource"
                        invalid-feedback="Monitoring source is required"
                      >
                        <b-form-input
                          id="monitoringSource"
                          v-model="monitoringSource"
                          required
                        ></b-form-input>
                      </b-form-group>
                    </b-col>
                    <b-col sm="12" md="6">
                      <b-form-group
                        label="حالة الامتثال"
                        label-for="complianceCase"
                        invalid-feedback="Compliance Case is required"
                      >
                        <b-form-select
                          id="complianceCase"
                          v-model="complianceCase"
                          :options="complianceCases"
                          required
                        ></b-form-select>
                      </b-form-group>
                    </b-col>
                    <b-col sm="12" md="6">
                      <b-form-group
                        label="الإجراء"
                        label-for="action"
                        invalid-feedback="Action source is required"
                      >
                        <b-form-input
                          id="action"
                          v-model="action"
                          required
                        ></b-form-input>
                      </b-form-group>
                    </b-col>
                    <b-col sm="12" md="6">
                      <b-form-group
                        label="النشاط"
                        label-for="active"
                        invalid-feedback="Active is required"
                      >
                        <b-form-input
                          id="active"
                          v-model="active"
                          required
                        ></b-form-input>
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
                        label="الاحتواء والاجراء الفعلي"
                        label-for="actual"
                        invalid-feedback="is required"
                      >
                        <b-form-input
                          id="actual"
                          v-model="actual"
                          required
                        ></b-form-input>
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
        :is-show="true"
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
      title: 'تقارير قيد التحقق',
      fields: [
        {
          key: 'reportCode',
          label: 'رمز التقرير',
        },
        {
          key: 'sampleCode',
          label: 'رمز العينة',
        },
        {
          key: 'casesCodes',
          label: 'رموز الحالات',
        },
        {
          key: 'releaseDate',
          label: 'تاريخ الإصدار ',
        },
        {
          key: 'monitoringSource',
          label: 'مصدر الرصد',
        },
        {
          key: 'complianceCase',
          label: 'حالة الامتثال',
        },
        {
          key: 'action',
          label: 'الإجراء',
        },
        {
          key: 'administration',
          label: 'الإدارة',
        },
        {
          key: 'active',
          label: 'النشاط',
        },
        {
          key: 'actual',
          label: 'الاحتواء والاجراء الفعلي',
        },
        {
          key: 'id',
          label: '',
        },
      ],
      items: [
        {
          reportCode: 'مثال',
          casesCodes: 'مثال',
          releaseDate: 'مثال',
          administration: 'مثال',
          monitoringSource: 'مثال',
          complianceCase: 'ممتثل',
          action: 'مثال',
          active: 'مثال',
          sampleCode: 'مثال',
          actual: 'مثال',
          id: 2,
        },
      ],
      reportCode: '',
      casesCodes: '',
      releaseDate: '',
      administration: '',
      monitoringSource: '',
      complianceCase: '',
      complianceCases: ['ممتثل', 'غير ممتثل'],
      action: '',
      active: '',
      sampleCode: '',
      actual: '',
      administrations: [
        'administration',
        'administration',
        'administration',
        'administration',
      ],
      action: '',
      reportsType: '',
      transformPoint: '',
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
