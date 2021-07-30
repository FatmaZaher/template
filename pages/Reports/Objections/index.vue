<template>
  <div>
    <Header :title="title" />
    <div class="content">
      <div class="header-content mt-2">
        <b-row>
          <b-col cols="6" class="d-flex align-items-center">
            <HeadPage :title="title" />
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
          key: 'complianceCase',
          label: 'حالة الامتثال',
        },
        {
          key: 'objectionReson',
          label: 'سبب الإعتراض',
        },
        {
          key: 'verificationCase',
          label: 'حالة التحقق',
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
          complianceCase: 'ممتثل',
          objectionReson: 'السبب',
          verificationCase: 'تم التحقق',
          id: 4,
        },
        {
          reportNo: '02',
          sampleNo: '002',
          complianceCase: 'غير ممتثل',
          objectionReson: 'السبب',
          verificationCase: 'تم التحقق',
          id: 4,
        },
        {
          reportNo: '03',
          sampleNo: '003',
          complianceCase: 'غير ممتثل',
          objectionReson: 'السبب',
          verificationCase: 'جاري التحقق',
          id: 4,
        },
        {
          reportNo: '04',
          sampleNo: '004',
          complianceCase: 'ممتثل',
          objectionReson: 'السبب',
          verificationCase: 'جاري التحقق',
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
