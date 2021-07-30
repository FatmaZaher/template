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
              <b-button class="btn main-btn mr-3">
                <nuxt-link :to="'/Monitoring/AddMonitoringSources'">
                  <PlusIcon />
                  <span class="ml-1"> {{ buttonTitle }}</span>
                </nuxt-link>
              </b-button>
              <b-button class="btn main-btn">
                <nuxt-link :to="'#'">
                  <DownloadIcon />
                  <span class="ml-1"> تصدير إكسل</span>
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
  </div>
</template>
<script>
export default {
  data() {
    return {
      title: 'مصادر الرصد',
      buttonTitle: 'إضافة مصدر رصد',
      fields: [
        {
          key: 'sourceCode',
          label: 'رمز المصدر',
        },
        {
          key: 'monitoringSource',
          label: 'إسم المصدر',
        },
        {
          key: 'id',
          label: '',
        },
      ],
      items: [
        {
          sourceCode: '50 C2',
          monitoringSource: 'إدارة الجودة',
          id: 1,
        },
        {
          sourceCode: '40 M8',
          monitoringSource: 'إدارة الجودة',
          id: 1,
        },
        {
          sourceCode: '88 C2',
          monitoringSource: 'إدارة الجودة',
          id: 1,
        },
        {
          sourceCode: '69 B2',
          monitoringSource: 'إدارة الجودة',
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
}
</script>

<style></style>
