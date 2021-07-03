<template>
  <div class="page-content">
    <Header />
    <div class="content">
      <b-button class="btn">
        <nuxt-link :to="'/VerificationProcess'">
          <span>عملية التحقق مسؤول الجودة</span>
        </nuxt-link>
      </b-button>
      <b-button class="btn">
        <nuxt-link :to="'/Objections/Objections1111'">
          <span>اعتراضات مسؤول الجودة</span>
        </nuxt-link>
      </b-button>
      <b-button class="btn">
        <nuxt-link :to="'/Justifications/Justifications1111'">
          <span>تبريرات مسؤول الجودة</span>
        </nuxt-link>
      </b-button>
      <b-button class="btn">
        <nuxt-link :to="'/VerificationResults'">
          <span>نتائج التحقق لمدير الجودة</span>
        </nuxt-link>
      </b-button>
      <b-button class="btn">
        <nuxt-link :to="'/ComprehensiveRecord'">
          <span>السجل الشامل</span>
        </nuxt-link>
      </b-button>
      <b-button class="btn">
        <nuxt-link :to="'/MonitoringProcess'">
          <span>عملية الرصد</span>
        </nuxt-link>
      </b-button>
      <b-button class="btn">
        <nuxt-link :to="'/MonitoringCases'">
          <span>حالات الرصد</span>
        </nuxt-link>
      </b-button>
    </div>
  </div>
</template>

<script>
export default {
}
</script>
<style scoped lang="scss">
.content {
  height: 700px;
}
</style>
