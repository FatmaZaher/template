<template>
  <div class="content">
    <div class="header-content">
      <b-row class="align-items-center">
        <b-col cols="6">
          <HeadPage :title="title"></HeadPage>
        </b-col>
        <b-col cols="6">
          <div class="d-flex justify-content-end">
            <b-button class="btn main-btn">
              <CheckIcon fill="#fff" />
              <span class="ml-1"> {{ buttonTitle }}</span>
            </b-button>
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
</template>

<script>
export default {
  data() {
    return {
      title: ' صلاحيات مديري الإدارات',
      buttonTitle: 'حفظ ',
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
}
</script>

<style lang="scss"></style>
