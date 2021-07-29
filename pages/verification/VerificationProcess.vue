<template>
  <div class="content subpage">
    <div class="text-center mt-4">
      <h5>{{ title }}</h5>
      <p>يرجى إدخال جميع بيانات التحقق</p>
    </div>
    <b-form ref="form" @submit.stop.prevent="">
      <VSelectInput
        labelfor="sampleNo"
        label="رقم العينة"
        :options="sampleNoList"
      />
      <VSelectInput
        labelfor="sampleName"
        label="اسم العينة"
        :options="sampleNameList"
      />
      <VSelectInput
        labelfor="sampleCode"
        label="رمز عينة "
        :options="sampleCodeList"
      />
      <VSelectInput
        labelfor="verificationCase"
        label="حالة التحقق"
        :options="verificationCaseList"
      />
      <div class="footer-button d-flex justify-content-between">
        <b-button type="submit" class="fot-btn main-btn w-100 mt-3 mr-3">
          <nuxt-link :to="'/NewSample'">
            <PlusIcon />
            <span class="ml-1">إضافة عينة جديدة </span>
          </nuxt-link>
        </b-button>
        <b-button @click="openModal" class="fot-btn main-btn w-100 mt-3">
          <SettingsIcon /><span class="ml-1">المقارنة والتحقق</span>
        </b-button>
        <AddModal
          v-model="openmodal"
          :compare-and-check="true"
          :save-button="false"
          size=""
        />
      </div>
    </b-form>
  </div>
</template>
<script>
export default {
  data() {
    return {
      title: 'عملية التحقق',
      openmodal: false,
      verificationCaseList: ['لم يتم التحقق بعد', 'جاري التحقق', 'تم التحقق'],
      sampleCodeList: ['samples 2', 'samples 3', 'samples 4'],
      sampleNameList: ['jjj', 'gg', 'ttt'],
      sampleNoList: ['01', '02', '03'],
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
