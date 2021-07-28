<template>
  <b-row class="w-100 m-0">
    <b-col md="5" class="d-flex align-items-center" order="2" order-md="1">
      <div class="formSection w-100">
        <div class="mb-4 mb-m-5">
          <h3>هل نسيت كلمة المرور ؟</h3>
        </div>
        <b-form ref="form" @submit.stop.prevent="">
          <Input
            labelfor="employeeEmail"
            labelname="البريد الإلكتروني"
            typeinput="email"
          />
          <div class="footer-button">
            <b-button type="submit" class="fot-btn main-btn w-100 my-3">
              <nuxt-link :to="'/Auth/ResetPassword'">
                إعادة تعيين كلمة المرور
              </nuxt-link>
            </b-button>
          </div>
          <p class="my-3 text-center">
            <nuxt-link :to="'/Auth/Login'">
              <span class="mr-1"> العودة إلى صفحة الدخول</span>
              <BackIcon />
            </nuxt-link>
          </p>
        </b-form>
      </div>
    </b-col>
    <b-col md="7" order="1" order-md="2">
      <div class="imageSection">
        <ForgotSvg />
      </div>
    </b-col>
  </b-row>
</template>
<script>
export default {
  layout: 'auth',
}
</script>

<style lang="scss" scoped></style>
