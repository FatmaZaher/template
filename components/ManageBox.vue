<template>
  <div class="manageBox">
    <b-row>
      <b-col>
        <b-form-group >
          <b-form-input
            type="text"
            v-model="search"
            placeholder="search the admin"
          ></b-form-input>
        </b-form-group>
      </b-col>
      <b-col></b-col>
    </b-row>
    <b-row class="w-100">
      <b-col
        cols="6"
        md="3"
        class="w-100 p-3 mb-3"
        v-for="department in filterdepartments"
        :key="department.administration"
        :department="department"
      >
        <nuxt-link :to="'/StaffRepresentation'">
          <div class="box p-3">
            <b-row>
              <b-col class="d-flex align-items-center">
                <span class="main-btn"> {{ department.compliancePers }} </span>
              </b-col>
              <b-col>
                <img :src="department.img" alt="" />
              </b-col>
            </b-row>
            <div class="text-center mt-3">
              {{ department.administration }}
            </div>
          </div>
        </nuxt-link>
      </b-col>
    </b-row>
  </div>
</template>
<script>
export default {
  data() {
    return {
      search: '',
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
  box-shadow: 0 3px 36px 0 rgba(0, 0, 0, 0.1);
  border-radius: 25px;
}
</style>
