<template>
  <div class="content">
    <b-button class="btn">
      <nuxt-link :to="'/VerificationProcess'">
        عملية التحقق مسؤول الجودة
      </nuxt-link>
    </b-button>
    <b-button class="btn">
      <nuxt-link :to="'/Objections/Objections1111'">
        اعتراضات مسؤول الجودة
      </nuxt-link>
    </b-button>
    <b-button class="btn">
      <nuxt-link :to="'/Justifications/Justifications1111'">
       تبريرات مسؤول الجودة
      </nuxt-link>
    </b-button>
    <b-button class="btn">
      <nuxt-link :to="'/VerificationResults'">
       نتائج التحقق لمدير الجودة
      </nuxt-link>
    </b-button>
    <b-button class="btn">
      <nuxt-link :to="'/ComprehensiveRecord'">
        السجل الشامل
      </nuxt-link>
    </b-button>
    <b-button class="btn">
      <nuxt-link :to="'/MonitoringProcess'">
        عملية الرصد
      </nuxt-link>
    </b-button>
    <b-button class="btn">
      <nuxt-link :to="'/MonitoringCases'">
       حالات الرصد
      </nuxt-link>
    </b-button>
  </div>
</template>

<script>
export default {}
</script>
<style scoped lang="scss">
.content {
  height: 700px;
}
</style>
