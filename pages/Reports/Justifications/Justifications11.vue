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
              <nuxt-link :to="'/Reports/Justifications/JustificationSubmit'">
                <PlusIcon />
                <span class="ml-1"> إضافة تبرير</span>
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
  </div></div>
  
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
