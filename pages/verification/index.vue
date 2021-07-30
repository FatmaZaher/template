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
      title: 'نتائج عملية التحقق',
      fields: [
        {
          key: 'reportNo',
          label: 'رقم التقرير',
        },
        {
          key: 'sampleCode',
          label: 'رمز العينة',
        },
        {
          key: 'verificationCase',
          label: 'حالة التحقق',
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
          reportNo: '04',
          sampleCode: '50 C2',
          verificationCase: 'تم التحقق',
          actual: 'مثال',
          id: 7,
        },
        {
          reportNo: '07',
          sampleCode: '40 C2',
          verificationCase: 'تم التحقق',
          actual: 'مثال',
          id: 7,
        },
        {
          reportNo: '09',
          sampleCode: '70 82',
          verificationCase: 'تم التحقق',
          actual: 'مثال',
          id: 7,
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
