<template>
  <div class="table-list">
    <b-table
      responsive
      :items="items"
      :fields="fields"
      small
      id="table-list"
      :per-page="perPage"
      :current-page="currentPage"
    >
      <template #cell(id)="data">
        <b-button class="" v-if="index">
          <span class="spanId"> {{ data.index }}</span>
        </b-button>
        <b-button class="btn" v-if="isObjection">
          <nuxt-link :to="'/Objections/objectionSubmit'">
            <span>إعتراض</span>
          </nuxt-link>
        </b-button>
        <b-button class="btn" v-if="isJustification">
          <nuxt-link :to="'/Justifications/justificationSubmit'">
            <span>تبرير</span>
          </nuxt-link>
        </b-button>
        <b-button v-b-modal.show-modal v-if="isShow" class="specialbtn">
          <img src="~/assets/images/Show.png" alt="" />
          <b-modal
            id="show-modal"
            ref="modal"
            title="عرض "
            @show="resetModal"
            @hidden="resetModal"
            @ok="handleOk"
          >
          </b-modal>
        </b-button>
        <b-button v-b-modal.edit-modal v-if="isEdit" class="specialbtn">
          <img src="~/assets/images/Edit.png" alt="" />
          <b-modal
            id="edit-modal"
            ref="modal"
            title="تعديل "
            @show="resetModal"
            @hidden="resetModal"
            @ok="handleOk"
          >
          </b-modal>
        </b-button>
        <b-button v-b-modal.delete-modal v-if="isDelete" class="specialbtn">
          <img src="~/assets/images/Delete.png" alt="" />
          <b-modal
            id="delete-modal"
            ref="modal"
            title="تأكيد الحذف "
            @show="resetModal"
            @hidden="resetModal"
            @ok="handleOk"
          >
            <div class="text-center">
              <img src="~/assets/images/Group 12868.png" alt="" />
              <p class="mt-3">هل أنت متأكد من عملية الحذف</p>
              <div class="footer-button d-flex justify-content-center">
                <b-button type="" class="fot-btn mx-3">حذف</b-button>
                <b-button type="" class="fot-btn mx-3">إغلاق</b-button>
              </div>
            </div>
          </b-modal>
        </b-button>
      </template>
    </b-table>
    <div class="pagin d-flex justify-content-center">
      <b-pagination
        v-model="currentPage"
        :total-rows="rows"
        :per-page="perPage"
        aria-controls="table-list"
      ></b-pagination>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    items: {
      type: Array,
      default: [],
    },
    rows: {
      type: null,
      default: '',
    },
    fields: {
      type: Array,
      default: [],
    },
    rows: {
      type: null,
      default: '',
    },
    id: {
      type: null,
      default: '',
    },
    index: {
      type: Boolean,
      default: false,
    },
    isObjection: {
      type: Boolean,
      default: false,
    },
    isJustification: {
      type: Boolean,
      default: false,
    },
    isDelete: {
      type: Boolean,
      default: false,
    },
    isShow: {
      type: Boolean,
      default: false,
    },
    isEdit: {
      type: Boolean,
      default: false,
    },
  },
  data() {
    return {
      perPage: 3,
      currentPage: 1,
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
