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
                <span>إضافة عملية رصد </span>
              </b-button>

              <b-modal
                id="add-modal"
                ref="modal"
                title="إضافة عملية رصد"
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
                        label="النطاق "
                        label-for="rang"
                        invalid-feedback="rang is required"
                      >
                        <b-form-input
                          id="rang"
                          v-model="rang"
                          required
                        ></b-form-input>
                      </b-form-group>
                    </b-col>
                    <b-col sm="12" md="6">
                      <b-form-group
                        label="الحالة التكرارية"
                        label-for="repetitiveCase"
                        invalid-feedback="ٌRepetitive Case is required"
                      >
                        <b-form-input
                          id="repetitiveCase"
                          v-model="repetitiveCase"
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
                        label="المسؤولية 1"
                        label-for="responsible1"
                        invalid-feedback="Responsible1 is required"
                      >
                        <b-form-input
                          id="responsible1"
                          v-model="responsible1"
                          required
                        ></b-form-input>
                      </b-form-group>
                    </b-col>
                    <b-col sm="12" md="6">
                      <b-form-group
                        label="المسؤولية 2"
                        label-for="responsible2"
                        invalid-feedback="Responsible2 is required"
                      >
                        <b-form-input
                          id="responsible2"
                          v-model="responsible2"
                          required
                        ></b-form-input>
                      </b-form-group>
                    </b-col>
                    <b-col sm="12" md="6">
                      <b-form-group
                        label="نسبة صحة الرصد"
                        label-for="monitoringPers"
                        invalid-feedback="monitoringPers is required"
                      >
                        <b-form-input
                          id="monitoringPers"
                          v-model="monitoringPers"
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
      title: 'نتائج عملية الرصد',
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
          key: 'rang',
          label: 'النطاق',
        },
        {
          key: 'repetitiveCase',
          label: 'الحالة التكرارية',
        },
        {
          key: 'monitoringCase',
          label: 'حالة الرصد',
        },
        {
          key: 'releaseDate',
          label: 'تاريخ الإصدار',
        },
        {
          key: 'administration',
          label: 'الإدارة',
        },
        {
          key: 'responsible1',
          label: 'المسؤولية 1',
        },
        {
          key: 'responsible2',
          label: 'المسؤولية 2',
        },
        {
          key: 'monitoringPers',
          label: 'نسبة صحة الرصد',
        },
        {
          key: 'id',
          label: '',
        },
      ],
      items: [
        {
          reportCode: 'مثال',
          sampleCode: 'مثال',
          rang: 'مثال',
          repetitiveCase: 'مثال',
          monitoringCase: 'مثال',
          releaseDate: 'مثال',
          administration: 'مثال',
          responsible1: 'مثال',
          responsible2: 'مثال',
          monitoringPers: 'مثال',
          id: 8,
        },
      ],

      reportCode: '',
      sampleCode: '',
      rang: '',
      repetitiveCase: '',
      monitoringCase: '',
      monitoringCases: ['صحيحة', 'خاطئة'],
      releaseDate: '',
      administration: '',
      administrations: [
        'administration',
        'administration',
        'administration',
        'administration',
      ],
      responsible1: '',
      responsible2: '',
      monitoringPers: '',
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
