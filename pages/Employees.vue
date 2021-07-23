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
              :is-employee-no="true"
              :is-employee-name="true"
              :is-employee-email="true"
              :is-section="true"
              :is-city="true"
              :is-administration="true"
              :is-job-name="true"
              :is-persntage="true"
              :is-mobile-no="true"
              :is-validity="true"
              :is-add-photo="true"
            />
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
      openmodal: false,
      title: 'الموظفين',
      buttonTitle: 'إضافة موظف',
      fields: [
        {
          key: 'employeeName',
          label: 'إسم الموظف',
        },
        {
          key: 'employeeNo',
          label: 'الرقم الوظيفي',
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
          label: 'الصلاحية'
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
  methods: {
    openModal() {
      this.openmodal = true
    },
  },
}
</script>

<style scoped lang="scss"></style>
