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
      title: 'التبريرات',
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
          key: 'justification',
          label: 'التبرير',
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
          key: 'id',
          label: '',
        },
      ],
      items: [
        {
          reportNo: '03',
          sampleNo: '003',
          justification: 'مثال',
          complianceCase: 'غير ممتثل',
          verificationCase: 'قيد التحقق',
          id: 6,
        },
        {
          reportNo: '07',
          sampleNo: '007',
          justification: 'مثال',
          complianceCase: 'ممتثل',
          verificationCase: 'جاري التحقق',
          id: 6,
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
