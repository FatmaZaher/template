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
        <div class="action">
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
          <b-button v-if="isShow" class="specialbtn">
            <img src="~/assets/images/Show.png" alt="" />
          </b-button>
          <b-button v-if="isEdit" class="specialbtn">
            <img src="~/assets/images/Edit.png" alt="" />
          </b-button>
          <b-button @click="openModal" v-if="isDelete" class="specialbtn">
            <img src="~/assets/images/Delete.png" alt="" />
            <AddModal
              v-model="openmodal"
              :modalTitle="deleteTitle"
              :is-delete-modal="true"
              :save-button="false"
            />
          </b-button>
        </div>
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
      openmodal: false,
      showTitle: 'عرض',
      editTitle: 'تعديل',
      deleteTitle: 'تأكيد الحذف',
    }
  },
  methods: {
    openModal() {
      this.openmodal = true
    },
  },
}
</script>
