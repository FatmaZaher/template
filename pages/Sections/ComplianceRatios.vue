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
              <nuxt-link :to="'#'">
                <DownloadIcon />
                <span class="ml-1"> تصدير إكسل</span>
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
      :is-edit="true"
      :is-delete="true"
    />
  </div>
</template>
<script>
export default {
  data() {
    return {
      title: 'نسب إمتثال الإدارات',
      buttonTitle: 'إضافة جديد ',
      openmodal: false,
      fields: [
        {
          key: 'administration',
          label: 'الإدارة',
        },
        {
          key: 'totalReports',
          label: 'إجمالي التقارير',
        },
        {
          key: 'monitoringRatio',
          label: 'نسبة الرصد',
        },
        {
          key: 'monitoringPers',
          label: 'نسبة صحة الرصد',
        },
         {
          key: 'employeesRepresen',
          label: 'عدد الموظفين الممثثليين',
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
          administration: 'إدارة التسويق',
          totalReports: '50',
          monitoringRatio: '50%',
          monitoringPers: '80%',
          employeesRepresen: '56',
          compliancePers: '80%',
          id: 11,
        },,
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
