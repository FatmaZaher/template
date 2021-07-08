<template>
  <b-row class="w-100 mr-0">
    <b-col md="5" class="d-flex align-items-center" order="2" order-md="1">
      <div class="formSection w-100">
        <div class="mb-4 mb-m-5">
          <h3>هل نسيت كلمة المرور ؟</h3>
        </div>
        <form ref="form" @submit.stop.prevent="">
          <b-form-group
            label="البريد الإلكتروني"
            label-for="email"
            invalid-feedback="Email is required"
          >
            <b-form-input id="email" type="email" required></b-form-input>
          </b-form-group>

          <div class="footer-button">
            <b-button type="submit" class="fot-btn w-100 my-3">
              <nuxt-link :to="'/ResetPassword'">
                إعادة تعيين كلمة المرور
              </nuxt-link>
            </b-button>
          </div>
          <p class="my-3 text-center">
            <nuxt-link :to="'/Login'">
              العودة إلى صفحة الدخول
              <i class="fas fa-chevron-circle-left"></i>
            </nuxt-link>
          </p>
        </form>
      </div>
    </b-col>
    <b-col md="7" order="1" order-md="2">
      <div class="imageSection">
        <img src="~/assets/images/forgot.svg" alt="Forgot image" />
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
