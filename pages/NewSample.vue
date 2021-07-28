<template>
  <div class="content subpage">
    <div class="text-center mt-4">
      <h5>{{ title }}</h5>
    </div>
    <b-form ref="form" @submit.stop.prevent="">
      <VSelectInput
        labelfor="sampleName"
        label="اسم العينة"
        :options="sampleNameList"
      />
      <VSelectInput
        labelfor="sampleNo"
        label="رقم العينة"
        :options="sampleNoList"
      />
      <VSelectInput
        labelfor="administration"
        label="الإدارة"
        :options="administrationList"
      />
      <VSelectInput labelfor="section" label="القسم" :options="sectionList" />
      <FormFile labelfor="newSampleFile" labelname="إضافة عينة من ملف" />
      <Textarea labelfor="roles" labelname="النقاط والشروط" />
      <div class="footer-button d-flex justify-content-between">
        <b-button type="submit" class="fot-btn main-btn w-100 mt-3 mr-3"
          >حفظ</b-button
        >
        <b-button type="" class="fot-btn main-btn w-100 mt-3 close-btn"
          ><nuxt-link :to="'/Action'"> إلغاء </nuxt-link>
        </b-button>
      </div>
    </b-form>
  </div>
</template>

<script>
export default {
  data() {
    return {
      openmodal: false,
      buttonTitle: '',
      title: 'إضافة عينة جديدة',
      sampleNameList: ['jjj', 'gg', 'ttt'],
      sampleNoList: ['01', '02', '03'],
      sectionList: [
        'قسم الشئون الماليه والمحاسبة',
        'قسم الموارد البشرية',
        'قسم الجوده',
        'قسم ادارة المخازن وتوفير المنتج',
      ],
      administrationList: [
        'إدارة التسويق',
        'الإدارة المالية',
        'إدارة الإنتاج',
        'إدارة التخطيط',
      ],
    }
  },
  methods: {
    openModal() {
      this.openmodal = true
    },
  },
}
</script>
<style scoped lang="scss"></style>
