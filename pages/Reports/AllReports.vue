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
              :is-report-code="true"
              :is-release-date="true"
              :is-samples-no="true"
              :is-monitoring-source="true"
              :is-report-no="true"
              :is-compliance-case="true"
              :is-administration="true"
              :is-action="true"
              :is-report-type="true"
              :is-verification-case="true"
            />
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
      openmodal: false,
      modalTitle: 'إضافة تقرير',
      fields: [
        {
          key: 'reportCode',
          label: 'رمز التقرير',
        },
        {
          key: 'reportNo',
          label: 'رقم التقرير',
        },
        {
          key: 'reportsType',
          label: 'نوع التقرير ',
        },
        {
          key: 'samplesNo',
          label: 'عدد العينات ',
        },
        {
          key: 'releaseDate',
          label: 'تاريخ الإصدار',
        },

        {
          key: 'monitoringSource',
          label: 'مصدر الرصد',
        },
        {
          key: 'administration',
          label: 'الإدارة',
        },
        {
          key: 'action',
          label: 'الإجراء',
        },
        {
          key: 'verificationCase',
          label: 'حالة التحقق',
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
          reportCode: 'Cac 01 22',
          reportNo: '01',
          reportsType: 'إداري',
          samplesNo: '20',
          releaseDate: 'Monday, July 12, 2021',
          monitoringSource: 'مثال',
          administration: 'إدارة التخطيط',
          action: 'تم التصحيح',
          verificationCase: 'جاري التحقق',
          complianceCase: 'ممتثل',
          id: 1,
        },
        {
          reportCode: 'BNS 88 02',
          reportNo: '02',
          reportsType: 'إداري',
          samplesNo: '20',
          releaseDate: 'Monday, July 12, 2021',
          monitoringSource: 'مثال',
          administration: 'إدارة التسويق',
          action: 'تم التصحيح',
          verificationCase: 'تم التحقق',
          complianceCase: 'غير ممتثل',
          id: 1,
        },
        {
          reportCode: 'Mn1 01 52',
          reportNo: '03',
          reportsType: 'إحصائي',
          samplesNo: '21',
          releaseDate: 'Monday, July 13, 2021',
          monitoringSource: 'مثال',
          administration: 'إدارة التخطيط',
          action: 'تم التصحيح',
          verificationCase: 'جاري التحقق',
          complianceCase: 'ممتثل',
          id: 1,
        },
        {
          reportCode: 'MJd 77 02',
          reportNo: '04',
          reportsType: 'إداري',
          samplesNo: '22',
          releaseDate: 'Monday, July 0, 2021',
          monitoringSource: 'مثال',
          administration: 'الإدارة المالية ',
          action: 'تم التصحيح',
          verificationCase: 'تم التحقق',
          complianceCase: ' غير ممتثل',
          id: 1,
        },
        {
          reportCode: 'CMM 01 28',
          reportNo: '05',
          reportsType: 'مالي',
          samplesNo: '23',
          releaseDate: 'Monday, July 4, 2021',
          monitoringSource: 'مثال',
          administration: 'إدارة التسويق',
          action: 'تم التصحيح',
          verificationCase: 'جاري التحقق',
          complianceCase: 'ممتثل',
          id: 1,
        },
        {
          reportCode: 'MVD 01 10',
          reportNo: '06',
          reportsType: 'إحصائي',
          samplesNo: '24',
          releaseDate: 'Monday, July 6, 2021',
          monitoringSource: 'مثال',
          administration: 'الإدارة المالية ',
          action: 'تم التصحيح',
          verificationCase: 'تم التحقق',
          complianceCase: 'غير ممتثل',
          id: 1,
        },
        {
          reportCode: 'CPP 22 01',
          reportNo: '07',
          reportsType: 'مالي',
          samplesNo: '25',
          releaseDate: 'Monday, July 17, 2021',
          monitoringSource: 'مثال',
          administration: 'إدارة الإنتاج',
          action: 'تم التصحيح',
          verificationCase: 'جاري التحقق',
          complianceCase: 'ممتثل',
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
  methods: {
    openModal() {
      this.openmodal = true
    },
  },
}
</script>

<style lang="scss"></style>
