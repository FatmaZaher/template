<template>
  <div>
    <Header :title="subPageTitle" />
    <div class="content">
      <div class="header-content mt-3">
        <b-row class="align-items-center">
          <b-col>
            <HeadPage :title="title" />
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
      title: ' إمتثال الموظفين للإدارة الواحدة',
      subPageTitle: 'إمتثال الموظفين',
      buttonTitle: 'إضافة جديد ',
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
}
</script>

<style lang="scss"></style>
