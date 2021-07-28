<template>
  <div class="content">
    <div class="header-content">
      <b-row class="align-items-center">
        <b-col cols="6">
          <HeadPage :title="title"></HeadPage>
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
</template>

<script>
export default {
  data() {
    return {
      title: ' صلاحيات مديرو الإدارات',
      buttonTitle: 'إضافة جديد ',
      openmodal: false,
      fields: [
        {
          key: 'all',
          label: '',
        },
        {
          key: 'administration',
          label: 'الإدارة',
          sortable: true,
        },
        {
          key: 'screen',
          label: 'الشاشة',
          sortable: true,
        },
        {
          key: 'view',
          label: 'عرض',
        },
        {
          key: 'save',
          label: 'حفظ',
        },
        {
          key: 'edit',
          label: 'تعديل',
        },
        {
          key: 'delete',
          label: 'حذف',
        },
        {
          key: 'print',
          label: 'طباعة',
        },
      ],
      items: [
        {
          administration: 'إدارة التسويق',
          screen: 'التبريرات',
        },
        ,
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
