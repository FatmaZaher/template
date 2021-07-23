<template>
  <div class="content">
    <div class="header-content">
      <b-row class="align-items-center">
        <b-col cols="6">
          <HeadPage :title="title"></HeadPage>
        </b-col>
        <b-col cols="6">
          <div class="d-flex justify-content-end">
            <b-button @click="openModal" class="btn main-btn">
              <i class="fas fa-plus"></i>
              <span>{{ buttonTitle }}</span>
            </b-button>
            <AddModal
              v-model="openmodal"
              :buttonTitle="buttonTitle"
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
      buttonTitle: 'إضافة قسم أو إدارة',
      openmodal: false,
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
          serialNo: '001',
          secORadmin: 'إدارة التسويق',
          id: 11,
        },
        {
          serialNo: '002',
          secORadmin: 'قسم الموارد البشرية',
          id: 11,
        },
        {
          serialNo: '003',
          secORadmin: 'إدارة التخطيط',
          id: 11,
        },
        {
          serialNo: '004',
          secORadmin: 'قسم ادارة المخازن وتوفير المنتج',
          id: 11,
        },
        {
          serialNo: '005',
          secORadmin: 'إدارة الإنتاج',
          id: 11,
        },
        {
          serialNo: '006',
          secORadmin: 'قسم الشئون الماليه والمحاسبة',
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
