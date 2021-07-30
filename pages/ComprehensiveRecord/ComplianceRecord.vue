<template>
  <div>
    <Header :title="title" />
    <div class="content">
      <div class="header-content">
        <b-row>
          <b-col cols="5" class="d-flex align-items-center">
            <HeadPage :title="title" />
          </b-col>
          <b-col cols="7">
            <div class="d-flex justify-content-end">
              <b-button @click="openModal" class="btn main-btn mr-md-3 mr-1">
                <PlusIcon />
                <span class="ml-1"> {{ buttonTitle }}</span>
              </b-button>
              <AddModal
                v-model="openmodal"
                :buttonTitle="buttonTitle"
                :is-administration="true"
                is-compliance-pers
              />
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
        :compliance-record="true"
      />
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      title: 'إمتثال الإدارات',
      buttonTitle: 'إضافة جديد',
      openmodal: false,
      fields: [
        {
          key: 'administration',
          label: 'الإدارة',
        },
        {
          key: 'compliancePers',
          label: 'نسبة الإمتثال',
        },
        {
          key: 'id',
          label: '',
        },
      ],
      items: [
        {
          administration: 'إدارة الإنتاج',
          compliancePers: '50%',
          id: 1,
        },
        {
          administration: 'إدارة الإنتاج',
          compliancePers: '50%',
          id: 1,
        },
        {
          administration: 'إدارة الإنتاج',
          compliancePers: '50%',
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
