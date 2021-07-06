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
          reportCode: 'BNS 88 02',
          sampleCode: '50 C2',
          rang: 'مثال',
          repetitiveCase: '11',
          monitoringCase: 'صحيحة',
          releaseDate: 'Tuesday, July 27, 2021',
          administration: 'إدارة التسويق',
          responsible1: 'مثال',
          responsible2: 'مثال',
          monitoringPers: '80%',
          id: 8,
        },
        {
          reportCode: 'MV 11 78',
          sampleCode: '40 M8',
          rang: 'مثال',
          repetitiveCase: '4',
          monitoringCase: 'غير صحيحة',
          releaseDate: 'Tuesday, July 27, 2021',
          administration: 'إدارة التسويق',
          responsible1: 'مثال',
          responsible2: 'مثال',
          monitoringPers: '56%',
          id: 8,
        },
        {
          reportCode: 'Ke 15 02',
          sampleCode: '88 C2',
          rang: 'مثال',
          repetitiveCase: '7',
          monitoringCase: 'صحيحة',
          releaseDate: 'Tuesday, July 27, 2021',
          administration: 'إدارة الإنتاج',
          responsible1: 'مثال',
          responsible2: 'مثال',
          monitoringPers: '77%',
          id: 8,
        },
        {
          reportCode: 'BNS 88 02',
          sampleCode: '69 B2',
          rang: 'مثال',
          repetitiveCase: '8',
          monitoringCase: 'غير صحيحة',
          releaseDate: 'Tuesday, July 27, 2021',
          administration: 'إدارة الإنتاج',
          responsible1: 'مثال',
          responsible2: 'مثال',
          monitoringPers: '50%',
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
