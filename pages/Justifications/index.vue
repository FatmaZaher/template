<template>
  <div class="content">
    <div class="header-content">
      <b-row class="align-items-center">
        <b-col cols="6">
          <HeadPage :title="title"></HeadPage>
        </b-col>
        <b-col cols="6">
          <div>
            <b-button class="btn">
              <nuxt-link :to="'/Justifications/justificationSubmit'">
                <i class="fas fa-plus"></i>
                <span>إضافة تبرير </span>
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
          key: 'id',
          label: '',
        },
      ],
      items: [
        {
          reportNo: '03',
          sampleNo: '003',
          justification: 'مثال',
          id: 4,
        },
        {
          reportNo: '07',
          sampleNo: '007',
          justification: 'مثال',
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
