<template>
  <div>
    <Header :title="title" />
    <div class="content">
      <b-row>
        <b-col md="4">
          <b-form-group label-cols="2" label="الإدارة" label-for="input-sm">
            <v-select
              class="input"
              v-model="search"
              :options="administrationList"
              dir="rtl"
            ></v-select>
            <span class="inputIcon"> <SearchIcon /></span>
          </b-form-group>
        </b-col>
        <b-col></b-col>
      </b-row>
      <b-row class="w-100 m-0">
        <b-col
          cols="6"
          md="3"
          class="w-100 mb-3"
          v-for="department in filterdepartments"
          :key="department.administration"
          :department="department"
        >
          <nuxt-link :to="'/StaffRepresentation'">
            <div class="box p-3">
              <b-row>
                <b-col
                  md="6"
                  class="
                    m-2 m-md-0
                    d-flex
                    align-items-center
                    justify-content-center
                  "
                >
                  <span class="main-btn">
                    {{ department.compliancePers }}
                  </span>
                </b-col>
                <b-col
                  md="6"
                  class="d-flex align-items-center justify-content-center"
                >
                  <img :src="department.img" alt="" />
                </b-col>
              </b-row>
              <div class="text-center mt-md-3 mt-1 adminName">
                {{ department.administration }}
              </div>
            </div>
          </nuxt-link>
        </b-col>
      </b-row>
    </div>
  </div>
</template>
<script>
export default {
  data() {
    return {
      search: '',
      title: 'إمتثال الإدارات',
      departments: [
        {
          administration: 'الإدارة المالية',
          img: require('~/assets/images/Screenshot_9.png'),
          compliancePers: '50%',
        },
        {
          administration: 'الإدارة التسويقية',
          img: require('~/assets/images/Screenshot_10.png'),
          compliancePers: '70%',
        },
        {
          administration: 'إدارة التخطيط',
          img: require('~/assets/images/Screenshot_12.png'),
          compliancePers: '90%',
        },
        {
          administration: 'إدارة الإنتاج',
          img: require('~/assets/images/Screenshot_13.png'),
          compliancePers: '60%',
        },
        {
          administration: 'إدارة الجودة',
          img: require('~/assets/images/Screenshot_13.png'),
          compliancePers: '75%',
        },
        {
          administration: 'إدارة الخدمات',
          img: require('~/assets/images/Screenshot_13.png'),
          compliancePers: '60%',
        },
      ],
      administrationList: [
        'إدارة التسويق',
        'الإدارة المالية',
        'إدارة الإنتاج',
        'إدارة التخطيط',
      ],
    }
  },
  computed: {
    filterdepartments: function () {
      return this.departments.filter((department) => {
        return department.administration.match(this.search)
      })
    },
  },
}
</script>
<style scoped lang="scss">
a {
  color: var(--text-color);
}
.box {
  box-shadow: 0 3px 36px 0 rgba(0, 0, 0, 0.2);
  border-radius: 25px;
  .main-btn {
    @media (max-width: 767px) {
      padding: 2px 10px;
    }
  }
  img {
    height: 80px;
    @media (max-width: 767px) {
      height: 50px;
    }
  }
  .adminName {
    @media (max-width: 767px) {
      font-size: 10px;
    }
  }
}
.inputIcon {
  top: 8px;
}
</style>
