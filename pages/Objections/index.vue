<template>
  <div class="content">
    <div class="header-content">
      <b-row class="row align-items-center text-left">
        <b-col cols="6">
          <HeadPage :title="title"></HeadPage>
        </b-col>
        <b-col cols="6">
          <div>
            <b-button class="btn">
              <nuxt-link :to="'/Objections/objectionSubmit'">
                <i class="fas fa-plus"></i>
                إضافة إعتراض
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
      title: 'الإعتراضات',
      fields: [
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
          id: 3,
        },
        {
          reportNo: '02',
          sampleNo: '002',
          objectionReson: 'السبب',
          id: 3,
        },
        {
          reportNo: '03',
          sampleNo: '003',
          objectionReson: 'السبب',
          id: 3,
        },
        {
          reportNo: '04',
          sampleNo: '004',
          objectionReson: 'السبب',
          id: 3,
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
