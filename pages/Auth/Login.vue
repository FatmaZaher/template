<template>
  <b-row class="w-100 m-0">
    <b-col md="5" class="d-flex align-items-center" order="2" order-md="1">
      <div class="formSection w-100">
        <div class="mb-4 mb-m-5">
          <h3>تسجيل الدخول</h3>
        </div>
        <b-form ref="form" @submit.stop.prevent="">
          <Input
            labelfor="employeeEmail"
            labelname="البريد الإلكتروني"
            typeinput="email"
          />
          <Input
            labelfor="password"
            labelname="كلمة المرور"
            typeinput="password"
          />
          <div class="forgot">
            <nuxt-link :to="'/Auth/ForgotPassword'">
              هل نسيت كلمة المرور ؟
            </nuxt-link>
          </div>
          <b-form-checkbox
            class="mt-3"
            id="checkbox-1"
            name="checkbox"
            value="accepted"
            unchecked-value="not_accepted"
          >
            تذكرني
          </b-form-checkbox>
          <p class="my-3">
            مستخدم جديد؟
            <nuxt-link :to="'/Auth/Register'"> إنشاء حساب </nuxt-link>
          </p>
          <div class="footer-button">
            <b-button type="submit" class="fot-btn main-btn w-100 mt-3">
              <nuxt-link :to="'/'"> دخول </nuxt-link>
            </b-button>
          </div>
        </b-form>
      </div>
    </b-col>
    <b-col md="7" order="1" order-md="2">
      <div class="imageSection">
        <LoginSvg />
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
