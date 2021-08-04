<template>
  <div>
    <Header :title="title" />
    <div class="content">
      <div class="header-content">
        <b-row>
          <b-col cols="4" class="d-flex align-items-center">
           
          </b-col>
          <b-col cols="8">
            <div class="d-flex justify-content-end">
              <b-button class="btn main-btn mr-md-3 mr-1">
                <nuxt-link :to="'/Reports/Archive/ArchiveAdd'">
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
        :is-show="true"
        :delete-text="deleteText"
      />
    </div>
  </div>
</template>
<script>
export default {
  data() {
    return {
      title: 'الأرشيف',
      buttonTitle: 'إضافة تقرير',
      deleteText: 'هل تريد حذف التقرير من قائمة التقارير؟',
      fields: [
        {
          key: 'reportNo',
          label: 'رقم التقرير',
        },
        {
          key: 'reportCode',
          label: 'رمز التقرير',
        },
        {
          key: 'releaseDate',
          label: 'تاريخ الإصدار ',
        },
        {
          key: 'caseCode',
          label: 'رمز الحالة',
        },
        {
          key: 'sampleCode',
          label: 'رمز العينة',
        },
        {
          key: 'sampleName',
          label: 'اسم العينة',
        },
        {
          key: 'administration',
          label: 'الإدارة',
        },
        {
          key: 'monitoringSource',
          label: 'مصدر الرصد',
        },
        {
          key: 'statusName',
          label: 'اسم الحالة',
        },
        {
          key: 'repetitiveCase',
          label: 'التكرارية',
        },
        {
          key: 'active',
          label: 'النشاط',
        },
        {
          key: 'id',
          label: '',
        },
      ],
      items: [
        {
          reportNo: '01',
          reportCode: 'BNS 88 02',
          releaseDate: 'الأربعاء، 21 يوليو 2021',
          caseCode: 'BNS 88',
          sampleCode: 'nn 10',
          sampleName: 'vdvdvd',
          administration: 'إدارة التسويق',
          monitoringSource: 'Source 2',
          statusName: 'status 2',
          repetitiveCase: '22',
          active: 'مثال',
          adminManager: 'Employee1',
          verificationResult: 'ممتثل',
          rangName: 'داخل نطاق الإدارة والحوكمة ',
          monitoringHealth: 'نعم',
          actual: '',
          qualityManagerNotes: '',
          stakeholderNotes: '',
          responsible1: 'مثال',
          responsible2: 'مثال',
          responsible3: 'مثال',
          id: 2,
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
