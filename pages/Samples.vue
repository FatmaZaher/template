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
                <span>إضافة عينة </span>
              </b-button>

              <b-modal
                id="add-modal"
                ref="modal"
                title="إضافة عينة"
                @show="resetModal"
                @hidden="resetModal"
                @ok="handleOk"
              >
                <form ref="form" @submit.stop.prevent="handleSubmit">
                  <b-row>
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
                        invalid-feedback="Responsible1 source is required"
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
                        invalid-feedback="Responsible2 Point is required"
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
                        label="المسؤولية 3"
                        label-for="responsible3"
                        invalid-feedback="Responsible3 Point is required"
                      >
                        <b-form-input
                          id="responsible3"
                          v-model="responsible3"
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
      title: 'العينات',
      fields: [
        {
          key: 'sampleName',
          label: 'إسم العينة',
        },
        {
          key: 'sampleCode',
          label: 'رمز العينة',
        },
        {
          key: 'samplesNo',
          label: 'عدد العينات',
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
          key: 'responsible3',
          label: 'المسؤولية 3',
        },
        {
          key: 'id',
          label: '',
        },
      ],
      items: [
        {
          sampleName: 'مثال',
          sampleCode: 'مثال',
          samplesNo: 'مثال',
          administration: 'مثال',
          responsible1: 'مثال',
          responsible2: 'مثال',
          responsible3: 'مثال',
          id: 10,
        },
      ],
      sampleName: '',
      sampleCode: '',
      samplesNo: '',
      administration: '',
      administrations: [
        'administration',
        'administration',
        'administration',
        'administration',
      ],
      responsible1: '',
      responsible2: '',
      responsible3: '',
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
