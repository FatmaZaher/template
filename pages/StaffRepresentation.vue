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
      title: ' إمتثال الموظفين للإدارة الواحدة',
      buttonTitle: 'إضافة جديد ',
      openmodal: false,
      fields: [
        {
          key: 'employeeNo',
          label: 'رقم الموظف',
        },
        {
          key: 'employeeName',
          label: ' الموظف المسؤول',
        },
        {
          key: 'administration',
          label: 'الإدارة',
        },
        {
          key: 'section',
          label: 'القسم',
        },
        {
          key: 'complianceCase',
          label: 'حالة الامتثال',
        },
        {
          key: 'id',
          label: '',
        },
      ],
      items: [
        {
          administration: 'إدارة التسويق',
          totalReports: '50',
          monitoringRatio: '50%',
          monitoringPers: '80%',
          employeesRepresen: '56',
          compliancePers: '80%',
          id: 11,
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
