<template>
  <div>
    <Header :subHead="false" />
    <div class="content">
      <b-row class="w-100 m-0">
        <b-col
          cols="12"
          md="4"
          class="w-100 mb-m-3 mb-5"
          v-for="card in cards"
          :key="card.title"
          :card="card"
        >
          <div class="box p-md-5 p-4 mb-m-0 mb-5">
            <div class="backCard">
              <div class="svgCard d-flex align-items-center">
                <component :is="card.icon"></component>
              </div>
            </div>
            <nuxt-link :to="card.link" class="w-100">
              <div class="main-btn text-center">
                {{ card.buttontitle }}
              </div>
            </nuxt-link>
          </div>
        </b-col>
      </b-row>
      <!--<div class="content">
      <b-button class="btn main-btn">
        <nuxt-link :to="'/Reports/Objections/Objections11'">
          اعتراضات مسؤول الإدارة
        </nuxt-link>
      </b-button>
      <b-button class="btn main-btn">
        <nuxt-link :to="'/Reports/Justifications/Justifications11'">
          تبريرات مسؤول الإدارة
        </nuxt-link>
      </b-button>
      <b-button class="btn main-btn">
        <nuxt-link :to="'/Reports/ManagerReports'">
          كافة التقارير مسؤول الإدارة
        </nuxt-link>
      </b-button>
      <b-button class="btn main-btn">
        <nuxt-link :to="'/VerificationProcess'">
          عملية التحقق مسؤول الجودة
        </nuxt-link>
      </b-button>
      <b-button class="btn main-btn">
        <nuxt-link :to="'/MonitoringProcess'"> عملية الرصد </nuxt-link>
      </b-button>
      <b-button class="btn main-btn">
        <nuxt-link :to="'/Error'"> error </nuxt-link>
      </b-button>
    </div>-->
    </div>
  </div>
</template>
<script>
export default {
  data() {
    return {
      cards: [
        {
          buttontitle: 'تقرير مستوى الثقة',
          icon: 'CheckListIcon',
          link: '/Reports/ConfidenceLevel',
        },
        {
          buttontitle: 'اللوحة القيادية',
          icon: 'DataIcon',
          link: '',
        },
        {
          buttontitle: 'تقرير إمتثال الإدارات',
          icon: 'ReportIcon',
          link: '/AdminCompliance',
        },
      ],
    }
  },
  computed: {},
}
</script>
<style scoped lang="scss">
.content {
  padding: 100px 40px;
}
.box {
  box-shadow: 0 3px 36px 0 rgba(0, 0, 0, 0.2);
  border-radius: 25px;
  .backCard {
    width: 100%;
    height: 180px;
    position: relative;
    .svgCard {
      height: 230px;
      width: 100%;
      background-image: radial-gradient(#f5fff4, var(--main-color));
      position: absolute;
      border-radius: 15px;
      padding: 30px;
      top: -80px;
    }
  }
  .main-btn {
    border-radius: 15px;
  }
  svg {
    height: 100%;
  }
}
</style>
