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
                title="إضافة قسم أو إدارة"
                @show="resetModal"
                @hidden="resetModal"
                @ok="handleOk"
              >
                <div class="tab_section">
                  <b-tabs content-class="mt-3">
                    <b-tab title="قسم" active>
                      <form ref="form" @submit.stop.prevent="handleSubmit">
                        <b-form-group
                          label="إسم القسم"
                          label-for="section"
                          invalid-feedback="Section is required"
                        >
                          <b-form-select
                            id="section"
                            :options="sections"
                            required
                          ></b-form-select>
                        </b-form-group>

                        <b-form-group
                          label="إسم مدير القسم"
                          label-for="managerSectionName"
                          invalid-feedback="Section Manager Name is required"
                        >
                          <b-form-input
                            id="managerSectionName"
                            v-model="managerSectionName"
                            required
                          ></b-form-input>
                        </b-form-group>
                        <div
                          class="footer-button d-flex justify-content-center"
                        >
                          <b-button type="submit" class="fot-btn"
                            >إضافة</b-button
                          >
                        </div>
                      </form>
                    </b-tab>
                    <b-tab title="إدارة">
                      <form ref="form" @submit.stop.prevent="handleSubmit">
                        <b-form-group
                          label="إسم الإدارة"
                          label-for="administration"
                          invalid-feedback="Administration is required"
                        >
                          <b-form-select
                            id="administration"
                            :options="administrations"
                            required
                          ></b-form-select>
                        </b-form-group>

                        <b-form-group
                          label="إسم مدير الإدارة"
                          label-for="managerAdminName"
                          invalid-feedback="Administration Manager Name is required"
                        >
                          <b-form-input
                            id="managerAdminName"
                            v-model="managerAdminName"
                            required
                          ></b-form-input>
                        </b-form-group>
                        <div
                          class="footer-button d-flex justify-content-center"
                        >
                          <b-button type="submit" class="fot-btn"
                            >إضافة</b-button
                          >
                        </div>
                      </form>
                    </b-tab>
                  </b-tabs>
                </div>
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
      title: 'الأقسام والإدارات',
      fields: [
        {
          key: 'serialNo',
          label: 'الرقم التسلسلي',
        },
        {
          key: 'secORadmin',
          label: 'الإدارة أو القسم',
        },
        {
          key: 'id',
          label: '',
        },
      ],
      items: [
        {
          serialNo: 40,
          secORadmin: 'مثال',
          id: 11,
        },
      ],
      section: '',
      sections: ['section 1', 'section 1', 'section 1', 'section 1'],
      managerSectionName: '',
      administration: '',
      managerAdminName: '',
      administrations: [
        'administration',
        'administration',
        'administration',
        'administration',
      ],
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

<style lang="scss"></style>
