<template>
  <div>
    <Header :title="title" />
    <div class="content">
      <div class="header-content">
        <b-row class="align-items-center">
          <b-col cols="6">
            <HeadPage :title="title" />
          </b-col>
          <b-col cols="6">
            <div class="d-flex justify-content-end">
              <b-button class="btn main-btn">
                <nuxt-link :to="'/Verification/Cases/AddCase'">
                  <PlusIcon />
                  <span class="ml-1"> {{ buttonTitle }}</span>
                </nuxt-link>
              </b-button>
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
      title: 'الحالات',
      buttonTitle: 'إضافة حالة ',
      fields: [
        {
          key: 'caseCode',
          label: 'رمز الحالة',
        },
        {
          key: 'statusName',
          label: 'اسم الحالة',
        },
        {
          key: 'administration',
          label: 'الإدارة',
        },
        {
          key: 'employeeName',
          label: ' الموظف المسؤول',
        },
        {
          key: 'caseDate',
          label: 'تاريخ الحالة',
        },
        {
          key: 'id',
          label: '',
        },
      ],
      items: [
        {
          caseCode: '00120',
          statusName: '',
          administration: 'إدارة التسويق',
          employeeName: '',
          caseDate: '',
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
}
</script>

<style lang="scss"></style>
