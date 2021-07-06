<template>
  <div class="content">
    <div class="header-content">
      <b-row class="align-items-center">
        <b-col cols="6">
          <HeadPage :title="title"></HeadPage>
        </b-col>
        <b-col cols="6">
          <div>
            <b-button @click="openModal" class="btn">
              <i class="fas fa-plus"></i>
              <span>{{ modalTitle }}</span>
            </b-button>
            <AddModal
              v-model="openmodal"
              :modalTitle="modalTitle"
              :is-section-modal="true"
            />
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
</template>

<script>
export default {
  data() {
    return {
      title: 'الأقسام والإدارات',
      modalTitle: 'إضافة قسم أو إدارة',
      openmodal: false,
      selected: '',
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
    }
  },
  computed: {
    rows() {
      return this.items.length
    },
  },
  methods: {
    openModal() {
      this.openmodal = true
    },
  },
}
</script>

<style lang="scss"></style>
