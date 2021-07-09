<template>
  <div class="content">
    Lorem ipsum dolor sit amet consectetur, adipisicing elit. Impedit iusto odit veritatis eaque necessitatibus, tempore saepe quisquam harum. Explicabo sapiente odit voluptatem ea est? Maxime ipsam id veritatis eos qui.
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
