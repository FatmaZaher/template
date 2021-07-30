<template>
  <div>
    <Header :title="title" />
    <div class="content">
      <div class="header-content">
        <b-row class="align-items-center">
          <b-col cols="6">
            <HeadPage :title="title" />
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
  </div>
</template>
<script>
export default {
  data() {
    return {
      title: ' مستوى الثقة',
      fields: [
        {
          key: 'reportNo',
          label: 'رقم التقرير',
        },
        {
          key: 'releaseDate',
          label: 'تاريخ الإصدار ',
        },
        {
          key: 'compliancePers',
          label: 'نسبة الإمتثال',
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
          reportNo: '01',
          releaseDate: '',
          complianceCase: 'ممتثل',
          compliancePers: '50%',
          id: 4,
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
