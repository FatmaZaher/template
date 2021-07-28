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
              <nuxt-link :to="'/Samples/AddSamples'">
                <PlusIcon />
                <span class="ml-1"> {{ buttonTitle }}</span>
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
      title: 'العينات',
      buttonTitle: 'إضافة عينة',
      fields: [
        {
          key: 'sampleNo',
          label: 'رقم العينة',
        },
        {
          key: 'sampleName',
          label: 'إسم العينة',
        },
        {
          key: 'administration',
          label: 'الإدارة',
        },
        {
          key: 'responsible1',
          label: 'المسؤولية 1',
        },
        {
          key: 'responsible2',
          label: 'المسؤولية 2',
        },
        {
          key: 'responsible3',
          label: 'المسؤولية 3',
        },
        {
          key: 'id',
          label: '',
        },
      ],
      items: [
        {
          sampleNo: '022',
          sampleName: 'مثال',
          administration: 'الإدارة المالية',
          responsible1: 'مثال',
          responsible2: 'مثال',
          responsible3: 'مثال',
          id: 10,
        },
        {
          sampleNo: '022',
          sampleName: 'مثال',
          administration: 'الإدارة المالية',
          responsible1: 'مثال',
          responsible2: 'مثال',
          responsible3: 'مثال',
          id: 10,
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

<style></style>
