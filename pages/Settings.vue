<template>
  <div>
    <Header :title="subPageTitle" />
    <div class="content">
      <div class="header-content">
        <b-form ref="form" @submit.stop.prevent="">
          <b-row>
            <b-col md="6">
              <Input
                labelfor="employeeName"
                labelname="الاسم"
                typeinput="text"
                icon="UserIcon"
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
                icon="EmailIcon"
              />
            </b-col>
            <b-col md="6">
              <Input
                labelfor="mobileNo"
                labelname="رقم الهاتف"
                typeinput="number"
                icon="MobileIcon"
              />
            </b-col>
            <b-col md="6">
              <VSelectInput
                labelfor="city"
                label="المدينة"
                :options="cityList"
                icon="CityIcon"
              />
            </b-col>
            <b-col md="6">
              <Input
                labelfor="newPassword"
                labelname="كلمة المرور الجديدة"
                typeinput="password"
                icon="PasswordIcon"
              />
            </b-col>
            <b-col md="6" offset-sm="3">
              <div class="footer-button d-flex justify-content-center">
                <b-button type="submit" class="fot-btn main-btn w-100">
                  تعديل البيانات
                </b-button>
              </div>
            </b-col>
          </b-row>
        </b-form>
      </div>
    </div>
  </div>
</template>
<script>
export default {
  data() {
    return {
      subPageTitle: 'الإعدادات',
      cityList: ['city 2', 'city 3', 'city 4', 'city 5', 'city 6', 'city 7'],
    }
  },
}
</script>

<style lang="scss"></style>
