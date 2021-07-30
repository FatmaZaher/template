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
              <b-button @click="openModal" class="btn main-btn">
                <PlusIcon />
                <span class="ml-1"> {{ buttonTitle }}</span>
              </b-button>
              <AddModal
                v-model="openmodal"
                :buttonTitle="buttonTitle"
                :is-monitoring-case="true"
                :is-monitoring-status-code="true"
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
  </div>
</template>

<script>
export default {
  data() {
    return {
      title: 'حالات الرصد',
      buttonTitle: 'إضافة حالة رصد',
      openmodal: false,
      fields: [
        {
          key: 'monitoringStatusCode',
          label: 'رمز حالة الرصد',
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
          monitoringStatusCode: '50 C2',
          monitoringCase: 'خاطئة',
          id: 1,
        },
        {
          monitoringStatusCode: '40 M8',
          monitoringCase: 'صحيحة',
          id: 1,
        },
        {
          monitoringStatusCode: '88 C2',
          monitoringCase: 'صحيحة',
          id: 1,
        },
        {
          monitoringStatusCode: '69 B2',
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
