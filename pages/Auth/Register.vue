<template>
  <b-row class="w-100 m-0">
    <b-col md="5" class="d-flex align-items-center" order="2" order-md="1">
      <div class="formSection w-100">
        <div class="mb-4 mb-m-5">
          <h3>إنشاء حساب</h3>
        </div>
        <b-form ref="form" @submit.stop.prevent="">
          <Input
            labelfor="username"
            labelname="اسم المستخدم"
            typeinput="text"
          />
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
          <b-form-checkbox
            class="mt-3"
            id="checkbox-1"
            name="checkbox"
            value="accepted"
            unchecked-value="not_accepted"
          >
            أوافق على سياسات الخصوصية
          </b-form-checkbox>
          <p class="my-3">
            تمتلك حساب؟
            <nuxt-link :to="'/Auth/Login'"> تسجيل الدخول </nuxt-link>
          </p>

          <div class="footer-button">
            <b-button type="submit" class="fot-btn main-btn w-100 mt-3">تسجيل</b-button>
          </div>
        </b-form>
      </div>
    </b-col>
    <b-col md="7" order="1" order-md="2">
      <div class="imageSection">
        <RegisterSvg />
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
