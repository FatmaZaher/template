<template>
  <div class="content">
    <div class="header-content">
      <b-row class="align-items-center">
        <b-col cols="6">
          <HeadPage :title="title"></HeadPage>
        </b-col>
        <b-col cols="6">
          <div>
            <b-button @click="openModal" class="btn">
              <i class="fas fa-plus"></i>
              <span>{{ modalTitle }}</span>
            </b-button>
            <AddModal
              v-model="openmodal"
              :modalTitle="modalTitle"
              :is-sample-code="true"
              :is-sample-name="true"
              :is-administration="true"
              :is-samples-no="true"
              :is-responsible1="true"
              :is-responsible2="true"
              :is-responsible3="true"
            />
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
      modalTitle: 'إضافة عينة',
      openmodal: false,
      fields: [
        {
          key: 'sampleName',
          label: 'إسم العينة',
        },
        {
          key: 'sampleCode',
          label: 'رمز العينة',
        },
        {
          key: 'samplesNo',
          label: 'عدد العينات',
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
          sampleName: 'مثال',
          sampleCode: '69 B2',
          samplesNo: '120',
          administration: 'الإدارة المالية',
          responsible1: 'مثال',
          responsible2: 'مثال',
          responsible3: 'مثال',
          id: 10,
        },
        {
          sampleName: 'مثال',
          sampleCode: '69 B2',
          samplesNo: '120',
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
  methods: {
    openModal() {
      this.openmodal = true
    },
  },
}
</script>

<style></style>
