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
              :is-sample-code="true"
              :is-rang="true"
              :is-repetitive-case="true"
              :is-monitoring-case="true"
              :is-release-date="true"
              :is-administration="true"
              :is-responsible1="true"
              :is-responsible2="true"
              :is-monitoring-pers="true"
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
      title: 'نتائج عملية الرصد',
      modalTitle: 'إضافة عملية رصد',
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
          key: 'rang',
          label: 'النطاق',
        },
        {
          key: 'repetitiveCase',
          label: 'الحالة التكرارية',
        },
        {
          key: 'monitoringCase',
          label: 'حالة الرصد',
        },
        {
          key: 'releaseDate',
          label: 'تاريخ الإصدار',
        },
        {
          key: 'administration',
          label: 'الإدارة',
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
          key: 'monitoringPers',
          label: 'نسبة صحة الرصد',
        },
        {
          key: 'id',
          label: '',
        },
      ],
      items: [
        {
          reportCode: 'مثال',
          sampleCode: 'مثال',
          rang: 'مثال',
          repetitiveCase: 'مثال',
          monitoringCase: 'مثال',
          releaseDate: 'مثال',
          administration: 'مثال',
          responsible1: 'مثال',
          responsible2: 'مثال',
          monitoringPers: 'مثال',
          id: 8,
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
