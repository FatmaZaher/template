<template>
  <div class="content subpage">
    <div class="text-center mt-4">
      <h6>{{ title }}</h6>
      <p>يرجى إدخال جميع بيانات التحقق</p>
    </div>
    <form ref="form" @submit.stop.prevent="">
      <b-row>
        <b-col sm="12" md="6">
          <b-form-group
            label="حالة التحقق"
            label-for="verificationCase"
            invalid-feedback="Verification Case is required"
          >
            <v-select dir="rtl" :options="verificationCases"></v-select>
          </b-form-group>
        </b-col>

        <b-col sm="12" md="6">
          <b-form-group
            label="رمز العينة"
            label-for="sampleCode"
            invalid-feedback="Sample Code is required"
          >
            <b-form-input id="sampleCode" required></b-form-input>
          </b-form-group>
        </b-col>

        <b-col sm="12" md="6">
          <b-form-group
            label="اسم العينة"
            label-for="sampleName"
            invalid-feedback="Sample Name Code is required"
          >
            <b-form-input id="sampleName" required></b-form-input>
          </b-form-group>
        </b-col>

        <b-col sm="12" md="6">
          <b-form-group
            label="رقم العينة"
            label-for="sampleNo"
            invalid-feedback="Sample Code is required"
          >
            <b-form-input id="sampleNo" required></b-form-input>
          </b-form-group>
        </b-col>
        <b-col sm="12">
          <div class="footer-button">
            <b-row>
              <b-col sm="12" md="6">
                <b-button class="fot-btn w-100 mt-3">
                  <i class="fas fa-plus"></i>
                  <span>إضافة عينة جديدة </span>
                </b-button>
              </b-col>
              <b-col sm="12" md="6">
                <b-button class="fot-btn w-100 mt-3">
                  <i class="fas fa-cog"></i>
                  <span>المقارنة والتحقق</span>
                </b-button>
              </b-col>
            </b-row>
          </div>
        </b-col>
      </b-row>
    </form>
  </div>
</template>

<script>
export default {
  data() {
    return {
      title: 'عملية التحقق',
      verificationCases: ['لم يتم التحقق بعد', 'جاري التحقق', 'تم التحقق'],
    }
  },
}
</script>
<style scoped lang="scss">
</style>
