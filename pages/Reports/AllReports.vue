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
              :is-sampels-no="true"
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
          reportCode: 40,
          releaseDate: 'مثال',
          samplesNo: 'مثال',
          monitoringSource: 'مثال',
          reportNo: 'مثال',
          complianceCase: 'ممتثل',
          administration: 'مثال',
          action: 'مثال',
          reportsType: 'مثال',
          verificationCase: 'مثال',
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

<style lang="scss">
</style>
