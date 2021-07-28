<template>
  <div class="content subpage">
    <div class="text-center mt-4">
      <h5>{{ title }}</h5>
    </div>
    <b-form ref="form" @submit.stop.prevent="">
      <b-row>
        <b-col md="6">
          <Input
            labelfor="employeeNo"
            labelname="الرقم الوظيفي"
            typeinput="number"
          />
        </b-col>
        <b-col md="6">
          <Input
            labelfor="employeeName"
            labelname="إسم الموظف"
            typeinput="text"
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
          <VSelectInput
            labelfor="section"
            label="القسم"
            :options="sectionList"
          />
        </b-col>
        <b-col md="6">
          <VSelectInput labelfor="city" label="المدينة" :options="cityList" />
        </b-col>
        <b-col md="6">
          <VSelectInput
            labelfor="administration"
            label="الإدارة"
            :options="administrationList"
          />
        </b-col>
        <b-col md="6">
          <Input
            labelfor="jobName"
            labelname="المسمى الوظيفي"
            typeinput="text"
          />
        </b-col>
        <b-col md="6">
          <Input
            labelfor="compliancePers"
            labelname="نسبة الإمتثال"
            typeinput="text"
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
          <VSelectInput
            labelfor="validity"
            label="الصلاحية"
            :options="validityList"
          />
        </b-col>
        <b-col md="6" offset-md="3">
          <FormFile labelfor="File" labelname="إضافة صورة" />
        </b-col>

        <div class="footer-button d-flex justify-content-between">
          <b-button type="submit" class="fot-btn main-btn w-100 mt-3 mr-3"
            >حفظ</b-button
          >
          <b-button type="" class="fot-btn main-btn w-100 mt-3 close-btn"
            >إلغاء</b-button
          >
        </div>
      </b-row>
    </b-form>
  </div>
</template>

<script>
export default {
  data() {
    return {
      title: 'إضافة موظف',
      administrationList: [
        'إدارة التسويق',
        'الإدارة المالية',
        'إدارة الإنتاج',
        'إدارة التخطيط',
      ],
      employeeNameList: ['Employee1', 'Employee3', 'Employee4', 'Employee5'],
      cityList: ['city 2', 'city 3', 'city 4', 'city 5', 'city 6', 'city 7'],
      sectionList: [
        'قسم الشئون الماليه والمحاسبة',
        'قسم الموارد البشرية',
        'قسم الجوده',
        'قسم ادارة المخازن وتوفير المنتج',
      ],
      validityList: ['validity1', 'validity2', 'validity3', 'validity4'],
    }
  },
}
</script>
<style scoped lang="scss">
.subpage form {
  width: 80%;
  margin: 50px auto;
}
</style>
