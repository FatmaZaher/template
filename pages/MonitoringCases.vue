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
              :is-monitoring-case="true"
            />
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
      title: 'حالات الرصد',
      modalTitle: 'إضافة حالة رصد',
      openmodal: false,
      fields: [
        {
          key: 'sampleCode',
          label: 'رمز العينة',
        },
        {
          key: 'monitoringCase',
          label: 'حالة الرصد',
        },
        {
          key: 'id',
          label: '',
        },
      ],
      items: [
        {
          sampleCode: '50 C2',
          monitoringCase: 'خاطئة',
          id: 1,
        },
        {
          sampleCode: '40 M8',
          monitoringCase: 'صحيحة',
          id: 1,
        },
        {
          sampleCode: '88 C2',
          monitoringCase: 'صحيحة',
          id: 1,
        },
        {
          sampleCode: '69 B2',
          monitoringCase: 'خاطئة',
          id: 1,
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
