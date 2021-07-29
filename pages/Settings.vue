<template>
  <div class="content">
    <div class="header-content">
      <b-form ref="form" @submit.stop.prevent="">
        <b-row class="w-100">
          <b-col md="6">
            <Input
              labelfor="employeeName"
              labelname="إسم الموظف"
              typeinput="text"
            />
          </b-col>
          <b-col md="6">
            <FormFile
              labelfor="employeePhoto"
              labelname="الصورة الشخصية"
              accept=".jpg, .jpeg , .png, .gif"
            />
          </b-col>
          <b-col md="6">
            <Input
              labelfor="employeeEmail"
              labelname="البريد الإلكتروني"
              typeinput="email"
            />
          </b-col>
          <b-col md="6">
            <Input
              labelfor="mobileNo"
              labelname="رقم الهاتف"
              typeinput="number"
            />
          </b-col>
          <b-col md="6">
            <VSelectInput labelfor="city" label="المدينة" :options="cityList" />
          </b-col>
        </b-row>
        <div class="mt-5">
          <h5 class="mb-4">كلمة المرور</h5>
          <b-row class="w-100">
            <b-col md="6">
              <Input
                labelfor="newPassword"
                labelname="كلمة المرور الجديدة"
                typeinput="password"
              /> </b-col
          ></b-row>
        </div>

        <b-button class="btn main-btn">
          <span class="ml-1"> {{ buttonTitle }}</span>
        </b-button>
      </b-form>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      buttonTitle: 'تعديل البيانات ',
      cityList: ['city 2', 'city 3', 'city 4', 'city 5', 'city 6', 'city 7'],
    }
  },
}
</script>

<style lang="scss"></style>
