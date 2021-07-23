<template>
  <div class="content subpage">
    <div class="text-center mt-4">
      <h6>{{ title }}</h6>
      <p>يرجى إدخال جميع بيانات التحقق</p>
    </div>
    <b-form ref="form" @submit.stop.prevent="">
      <VSelectInput
        labelfor="verificationCase"
        label="حالة التحقق"
        :options="verificationCaseList"
      />
      <VSelectInput
        labelfor="sampleCode"
        label="رمز عينة "
        :options="sampleCodeList"
      />
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
      <div class="footer-button d-flex justify-content-between">
        <b-button type="submit" class="fot-btn main-btn w-100 mt-3 mr-3">
          <nuxt-link :to="'/NewSample'">
            <i class="fas fa-plus"></i>
            <span>إضافة عينة جديدة </span>
          </nuxt-link>
        </b-button>
        <b-button @click="openModal" class="fot-btn main-btn w-100 mt-3">
          <i class="fas fa-cog"></i> <span>المقارنة والتحقق</span>
        </b-button>
        <AddModal
          v-model="openmodal"
          :compare-and-check="true"
          :save-button="false"
        />
      </div>
    </b-form>
  </div>
</template>
<script>
export default {
  data() {
    return {
      openmodal: false,
      title: 'عملية التحقق',
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
