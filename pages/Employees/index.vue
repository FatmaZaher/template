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
                <nuxt-link :to="'/Employees/AddEmployees'">
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
      title: 'الموظفين',
      buttonTitle: 'إضافة موظف',
      fields: [
        {
          key: 'employeeNo',
          label: 'الرقم الوظيفي',
        },
        {
          key: 'employeeName',
          label: 'إسم الموظف',
        },
        {
          key: 'employeePhoto',
          label: 'صورة المستخدم',
        },
        {
          key: 'employeeEmail',
          label: 'البريد الإلكتروني',
        },
        {
          key: 'city',
          label: 'المدينة',
        },
        {
          key: 'section',
          label: 'القسم',
        },
        {
          key: 'administration',
          label: 'الإدارة',
        },
        {
          key: 'validity',
          label: 'الصلاحية',
        },
        {
          key: 'jobName',
          label: 'المسمى الوظيفي',
        },

        {
          key: 'compliancePers',
          label: 'نسبة الإمتثال',
        },
        {
          key: 'id',
          label: '',
        },
      ],
      items: [
        {
          employeeNo: '00001',
          employeeName: 'محمد',
          section: 'قسم الجوده',
          administration: 'إدارة التسويق',
          employeeEmail: 'mohammed@gmail.com',
          jobName: 'نائب المدير',
          compliancePers: '85%',
          id: 9,
        },
        {
          employeeNo: '00002',
          employeeName: 'سوسن',
          section: 'قسم الموارد البشرية',
          administration: 'الإدارة المالية',
          employeeEmail: 'swsan@gmail.com',
          jobName: 'موظف إداري',
          compliancePers: '78%',
          id: 9,
        },
        {
          employeeNo: '00003',
          employeeName: 'علي',
          section: 'قسم ادارة المخازن وتوفير المنتج',
          administration: 'إدارة التخطيط',
          employeeEmail: 'ali@gmail.com',
          jobName: 'موظف إداري',
          compliancePers: '41%',
          id: 9,
        },
        {
          employeeNo: '00004',
          employeeName: 'علياء',
          section: 'قسم الجوده',
          administration: 'إدارة التسويق',
          employeeEmail: 'aliaa@gmail.com',
          jobName: 'موظف إداري',
          compliancePers: '85%',
          id: 9,
        },
        {
          employeeNo: '00005',
          employeeName: 'محمد',
          section: 'قسم الشئون الماليه والمحاسبة',
          administration: 'إدارة الإنتاج',
          employeeEmail: 'mohammed@gmail.com',
          jobName: 'نائب المدير',
          compliancePers: '85%',
          id: 9,
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

<style scoped lang="scss"></style>
