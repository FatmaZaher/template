<template>
  <b-row class="w-100 mr-0">
    <b-col md="5" class="d-flex align-items-center" order="2" order-md="1">
      <div class="formSection w-100">
        <div class="mb-4 mb-m-5">
          <h3>إنشاء حساب</h3>
        </div>
        <form ref="form" @submit.stop.prevent="">
          <b-form-group
            label="اسم المستخدم"
            label-for="name"
            invalid-feedback="Name is required"
          >
            <b-form-input id="Name" type="text" required></b-form-input>
          </b-form-group>

          <b-form-group
            label="البريد الإلكتروني"
            label-for="email"
            invalid-feedback="Email is required"
          >
            <b-form-input id="email" type="email" required></b-form-input>
          </b-form-group>

          <b-form-group
            label="كلمة المرور"
            label-for="password"
            invalid-feedback="password is required"
          >
            <b-form-input id="password" type="password" required></b-form-input>
          </b-form-group>
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
            <nuxt-link :to="'/Login'"> تسجيل الدخول </nuxt-link>
          </p>

          <div class="footer-button">
            <b-button type="submit" class="fot-btn w-100 mt-3">تسجيل</b-button>
          </div>
        </form>
      </div>
    </b-col>
    <b-col md="7" order="1" order-md="2">
      <div class="imageSection">
        <img src="~/assets/images/register.svg" alt="Resgister image" />
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
