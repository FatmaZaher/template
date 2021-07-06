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
              :is-monitoring-source="true"
              :is-compliance-case="true"
              :is-administration="true"
              :is-action="true"
              :is-cases-code="true"
              :is-active="true"
              :is-actual="true"
              :is-sample-code="true"
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
      title: 'تقارير قيد التحقق',
      modalTitle: 'إضافة تقرير قيد التحقق',
      openmodal: false,
      fields: [
        {
          key: 'reportCode',
          label: 'رمز التقرير',
        },
        {
          key: 'sampleCode',
          label: 'رمز العينة',
        },
        {
          key: 'casesCodes',
          label: 'رموز الحالات',
        },
        {
          key: 'releaseDate',
          label: 'تاريخ الإصدار ',
        },
        {
          key: 'monitoringSource',
          label: 'مصدر الرصد',
        },
        {
          key: 'complianceCase',
          label: 'حالة الامتثال',
        },
        {
          key: 'action',
          label: 'الإجراء',
        },
        {
          key: 'administration',
          label: 'الإدارة',
        },
        {
          key: 'active',
          label: 'النشاط',
        },
        {
          key: 'actual',
          label: 'الاحتواء والاجراء الفعلي',
        },
        {
          key: 'id',
          label: '',
        },
      ],
      items: [
        {
          reportCode: 'BNS 88 02',
          sampleCode: '69 B2',
          casesCodes: '56 BN',
          releaseDate: 'Sunday, July 25, 2021',
          administration: 'إدارة التسويق',
          monitoringSource: 'مثال',
          complianceCase: 'ممتثل',
          action: 'تم التصحيح',
          active: 'مثال',
          actual: 'مثال',
          id: 2,
        },
        {
          reportCode: 'BNS 88 02',
          sampleCode: '69 B2',
          casesCodes: '56 BN',
          releaseDate: 'Sunday, July 25, 2021',
          administration: 'إدارة التسويق',
          monitoringSource: 'مثال',
          complianceCase: 'ممتثل',
          action: 'تم التصحيح',
          active: 'مثال',
          actual: 'مثال',
          id: 2,
        },
        {
          reportCode: 'BNS 88 02',
          sampleCode: '69 B2',
          casesCodes: '56 BN',
          releaseDate: 'Sunday, July 25, 2021',
          administration: 'إدارة التسويق',
          monitoringSource: 'مثال',
          complianceCase: 'ممتثل',
          action: 'تم التصحيح',
          active: 'مثال',
          actual: 'مثال',
          id: 2,
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

<style></style>
