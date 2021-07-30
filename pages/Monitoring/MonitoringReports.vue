<template>
  <div>
    <Header :title="subPageTitle" />
    <div class="content">
      <div class="header-content">
        <b-row class="align-items-center">
          <b-col cols="6">
            <HeadPage :title="title" />
          </b-col>
          <b-col cols="6">
            <div class="d-flex justify-content-end">
              <b-button @click="openModal" class="btn main-btn mr-3">
                <PlusIcon />
                <span class="ml-1"> {{ buttonTitle }}</span>
              </b-button>
              <b-button class="btn main-btn">
                <nuxt-link :to="'#'">
                  <DownloadIcon />
                  <span class="ml-1"> تصدير إكسل</span>
                </nuxt-link>
              </b-button>
              <AddModal
                v-model="openmodal"
                :buttonTitle="buttonTitle"
                :is-report-code="true"
                :is-sample-code="true"
                :is-rang-name="true"
                :is-repetitive-case="true"
                :is-monitoring-case-select="true"
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
  </div>
</template>

<script>
export default {
  data() {
    return {
      title: 'نتائج عملية الرصد',
      subPageTitle: 'تقارير الرصد',
      buttonTitle: 'إضافة عملية رصد',
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
          key: 'rangName',
          label: 'اسم النطاق',
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
          key: 'qualityManagerNotes',
          label: 'ملاحظات مدير الجودة',
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
          rangName: 'مثال',
          repetitiveCase: '11',
          monitoringCase: 'صحيحة',
          releaseDate: 'Tuesday, July 27, 2021',
          administration: 'إدارة التسويق',
          responsible1: 'مثال',
          responsible2: 'مثال',
          monitoringPers: '80%',
          qualityManagerNotes: '',
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
