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
      modalTitle: 'إضافة موظف',
      fields: [
        {
          key: 'employeeNo',
          label: 'الرقم الوظيفي',
        },
        {
          key: 'employeeName',
          label: 'الإسم',
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
          key: 'employeeEmail',
          label: 'البريد الإلكتروني',
        },
        {
          key: 'jobName',
          label: 'المسمى الوظيفي',
        },
        {
          key: 'CompliancePers',
          label: 'نسبة الإمتثال',
        },
        {
          key: 'id',
          label: '',
        },
      ],
      items: [
        {
          employeeNo: 'مثال',
          employeeName: 'مثال',
          section: 'مثال',
          administration: 'مثال',
          employeeEmail: 'مثال',
          jobName: 'مثال',
          CompliancePers: 'مثال',
          id: 9,
        },
        {
          employeeNo: 'مثال',
          employeeName: 'مثال',
          section: 'مثال',
          administration: 'مثال',
          employeeEmail: 'مثال',
          jobName: 'مثال',
          CompliancePers: 'مثال',
          id: '',
        },
         {
          employeeNo: 'مثال',
          employeeName: 'مثال',
          section: 'مثال',
          administration: 'مثال',
          employeeEmail: 'مثال',
          jobName: 'مثال',
          CompliancePers: 'مثال',
          id: 9,
        },
         {
          employeeNo: 'مثال',
          employeeName: 'مثال',
          section: 'مثال',
          administration: 'مثال',
          employeeEmail: 'مثال',
          jobName: 'مثال',
          CompliancePers: 'مثال',
          id: 9,
        },
         {
          employeeNo: 'مثال',
          employeeName: 'مثال',
          section: 'مثال',
          administration: 'مثال',
          employeeEmail: 'مثال',
          jobName: 'مثال',
          CompliancePers: 'مثال',
          id: 9,
        },
         {
          employeeNo: 'مثال',
          employeeName: 'مثال',
          section: 'مثال',
          administration: 'مثال',
          employeeEmail: 'مثال',
          jobName: 'مثال',
          CompliancePers: 'مثال',
          id: 9,
        },
         {
          employeeNo: 'مثال',
          employeeName: 'مثال',
          section: 'مثال',
          administration: 'مثال',
          employeeEmail: 'مثال',
          jobName: 'مثال',
          CompliancePers: 'مثال',
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
