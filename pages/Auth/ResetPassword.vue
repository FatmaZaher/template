<template>
  <b-row class="w-100 mr-0">
    <b-col md="5" class="d-flex align-items-center" order="2" order-md="1">
      <div class="formSection w-100">
        <div class="mb-4 mb-m-5">
          <h3>إعادة تعيين كلمة المرور</h3>
        </div>
        <b-form ref="form" @submit.stop.prevent="">
          <Input
            labelfor="newPassword"
            labelname="كلمة المرور الجديدة"
            typeinput="password"
          />
          <Input
            labelfor="confirmPassword"
            labelname="تأكيد كلمة المرور"
            typeinput="password"
          />

          <div class="footer-button">
            <b-button type="submit" class="fot-btn main-btn w-100 my-3">
              تعيين كلمة مرور جديدة
            </b-button>
          </div>
          <p class="my-3 text-center">
            <nuxt-link :to="'/Auth/Login'">
              العودة إلى صفحة الدخول
              <i class="fas fa-chevron-circle-left"></i>
            </nuxt-link>
          </p>
        </b-form>
      </div>
    </b-col>
    <b-col md="7" order="1" order-md="2">
      <div class="imageSection">
        <img src="~/assets/images/reset.svg" alt="Reset image" />
      </div>
    </b-col>
  </b-row>
</template>
<script>
export default {
  layout: 'auth',
}
</script>
<style lang="scss" scoped>
.imageSection {
  img {
    height: 450px;
  }
}
@media (max-width: 767px) {
  .formSection {
    padding: 50px 20px 0 20px;
  }
}
</style>
