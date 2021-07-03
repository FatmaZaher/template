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
                <span>إضافة تقرير </span>
              </b-button>

              <b-modal
                id="add-modal"
                ref="modal"
                title="إضافة تقرير"
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
                        label="عدد العينات"
                        label-for="samplesNo"
                        invalid-feedback="Sample No. is required"
                      >
                        <b-form-input
                          id="samplesNo"
                          v-model="samplesNo"
                          required
                        ></b-form-input>
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
                        label="رقم التقرير"
                        label-for="reportNo"
                        invalid-feedback="Report No. source is required"
                      >
                        <b-form-input
                          id="reportNo"
                          v-model="reportNo"
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
                        label="نوع التقرير"
                        label-for="reportsType"
                        invalid-feedback="Report Type is required"
                      >
                        <b-form-select
                          id="reportsType"
                          v-model="reportsType"
                          :options="reportsTypes"
                          required
                        ></b-form-select>
                      </b-form-group>
                    </b-col>
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
        :is-objection="true"
        :is-justification="true"
      />
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      title: 'كافة التقارير',
      fields: [
        {
          key: 'reportCode',
          label: 'رمز التقرير',
        },
        {
          key: 'reportNo',
          label: 'رقم التقرير',
        },
        {
          key: 'reportsType',
          label: 'نوع التقرير ',
        },
        {
          key: 'samplesNo',
          label: 'عدد العينات ',
        },
        {
          key: 'releaseDate',
          label: 'تاريخ الإصدار',
        },

        {
          key: 'monitoringSource',
          label: 'مصدر الرصد',
        },
        {
          key: 'administration',
          label: 'الإدارة',
        },
        {
          key: 'action',
          label: 'الإجراء',
        },
        {
          key: 'verificationCase',
          label: 'حالة التحقق',
        },
        {
          key: 'complianceCase',
          label: 'حالة الامتثال',
        },
        {
          key: 'id',
          label: '',
        },
      ],
      items: [
        {
          reportCode: 40,
          releaseDate: 'مثال',
          samplesNo: 'مثال',
          monitoringSource: 'مثال',
          reportNo: 'مثال',
          complianceCase: 'ممتثل',
          administration: 'مثال',
          action: 'مثال',
          reportsType: 'مثال',
          verificationCase: 'مثال',
          id: 1,
        },
      ],
      reportCode: '',
      releaseDate: '',
      samplesNo: '',
      monitoringSource: '',
      reportNo: '',
      complianceCase: '',
      complianceCases: ['ممتثل', 'غير ممتثل'],
      administration: '',
      administrations: [
        'administration',
        'administration',
        'administration',
        'administration',
      ],
      action: '',
      reportsType: '',
      reportsTypes: ['Type', 'Type', 'Type', 'Type'],
      verificationCase: '',
      verificationCases: ['لم يتم التحقق بعد', 'جاري التحقق', 'تم التحقق'],
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
