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
              <nuxt-link :to="'/Reports/ReportIssuance'">
                {{ buttonTitle }}
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
      :is-objection="true"
      :is-justification="true"
    />
  </div>
</template>
<script>
export default {
  data() {
    return {
      title: 'كافة التقارير',
      buttonTitle: 'إضافة تقرير',
      fields: [
        {
          key: 'reportNo',
          label: 'رقم التقرير',
        },
        {
          key: 'reportCode',
          label: 'رمز التقرير',
        },
        {
          key: 'releaseDate',
          label: 'تاريخ الإصدار ',
        },
        {
          key: 'caseCode',
          label: 'رمز الحالة',
        },
        {
          key: 'sampleCode',
          label: 'رمز العينة',
        },
        {
          key: 'sampleName',
          label: 'اسم العينة',
        },
        {
          key: 'administration',
          label: 'الإدارة',
        },
        {
          key: 'monitoringSource',
          label: 'مصدر الرصد',
        },
        {
          key: 'statusName',
          label: 'اسم الحالة',
        },
        {
          key: 'repetitiveCase',
          label: 'التكرارية',
        },
        {
          key: 'active',
          label: 'النشاط',
        },
         {
          key: 'adminManager',
          label: 'مدير الإدارة',
        },
        {
          key: 'verificationResult',
          label: 'نتيجة التحقق',
        },
        {
          key: 'rangName',
          label: 'اسم النطاق',
        },
        {
          key: 'monitoringHealth',
          label: 'هل الرصد خاطئ؟',
        },
        {
          key: 'monitoringHealth',
          label: 'هل الرصد خاطئ؟',
        },
        {
          key: 'actual',
          label: 'الإحتواء والإجراء الفوري',
        },
        {
          key: 'qualityManagerNotes',
          label: 'ملاحظات مدير الجودة',
        },
        {
          key: 'stakeholderNotes',
          label: 'ملاحظات الجهة المعنية',
        },
        {
          key: 'responsible1',
          label: 'المسؤولية 1',
        },
        {
          key: 'responsible2',
          label: 'المسؤولية 2',
        },
        {
          key: 'responsible3',
          label: 'المسؤولية 3',
        },
        {
          key: 'id',
          label: '',
        },
      ],
      items: [
        {
          reportNo: '01',
          reportCode: 'BNS 88 02',
          releaseDate: 'Sunday, July 25, 2021',
          caseCode: 'BNS 88',
          sampleCode: 'nn 10',
          sampleName: 'vdvdvd',
          administration: 'إدارة التسويق',
          monitoringSource: 'Source 2',
          statusName: 'status 2',
          repetitiveCase: '22',
          active: 'مثال',
          adminManager: 'Employee1',
          verificationResult: 'ممتثل',
          rangName: 'داخل نطاق الإدارة والحوكمة ',
          monitoringHealth: 'نعم',
          actual: 'مثال',
          qualityManagerNotes: 'مثال',
          stakeholderNotes: 'مثال',
          responsible1: 'مثال',
          responsible2: 'مثال',
          responsible3: 'مثال',
          id: 1,
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
