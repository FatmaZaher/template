<template>
  <div class="page-content">
    <Header :title="title" />
    <div class="content">
      <div class="header-content">
        <div class="row align-items-center">
          <div class="col-6">
            <HeadPage :title="title"></HeadPage>
          </div>
        </div>
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
          key: 'complianceCase',
          label: 'حالة الامتثال',
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
          reportNo: 40,
          sampleCode: 'مثال',
          complianceCase: 'مثال',
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
