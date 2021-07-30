<template>
  <div class="content">
    <div class="header-content">
      <b-row>
        <b-col cols="6" class="d-flex align-items-center">
          <HeadPage :title="title" />
        </b-col>
        <b-col cols="6">
          <div class="d-flex justify-content-end">
            <b-button class="btn main-btn">
              <nuxt-link :to="'/Reports/Objections/objectionSubmit'">
                <PlusIcon />
                <span class="ml-1"> إضافة إعتراض</span>
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
      title: 'الإعتراضات',
      fields: [,
        {
          key: 'reportNo',
          label: 'رقم التقرير',
        },
        {
          key: 'sampleNo',
          label: 'رقم العينة',
        },
        {
          key: 'objectionReson',
          label: 'سبب الإعتراض',
        },
        {
          key: 'id',
          label: '',
        },
      ],
      items: [
        {
          reportNo: '01',
          sampleNo: '001',
          objectionReson: 'السبب',
        },
        {
          reportNo: '02',
          sampleNo: '002',
          objectionReson: 'السبب',
        },
        {
          reportNo: '03',
          sampleNo: '003',
          objectionReson: 'السبب',
        },
        {
          reportNo: '04',
          sampleNo: '004',
          objectionReson: 'السبب',
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
<style lang="scss" scoped>
</style>
