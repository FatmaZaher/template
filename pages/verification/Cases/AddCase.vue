<template>
  <div class="content subpage">
    <div class="text-center mt-4">
      <h5>{{ title }}</h5>
    </div>
    <b-form ref="form" @submit.stop.prevent="">
      <Input labelfor="caseCode" labelname="رمز الحالة" typeinput="text" />
      <Input labelfor="statusName" labelname="اسم الحالة" typeinput="text" />
      <DatepickerInput labelfor="caseDate" labelname="تاريخ الحالة" />
      <VSelectInput
        labelfor="administration"
        label="الإدارة"
        :options="administrationList"
      />
      <VSelectInput
        labelfor="caseEmployee"
        label="الموظف المسؤول"
        :options="employeeNameList"
      />
      <FormFile labelfor="caseFile" labelname="رفع الحالات من ملف" />

      <div class="footer-button d-flex justify-content-between">
        <b-button type="submit" class="fot-btn main-btn w-100 mt-3 mr-3"
          >حفظ</b-button
        >
        <b-button type="" class="fot-btn main-btn w-100 mt-3 close-btn"
          >إلغاء</b-button
        >
      </div>
    </b-form>
  </div>
</template>

<script>
export default {
  data() {
    return {
      title: 'إضافة حالة',
      administrationList: [
        'إدارة التسويق',
        'الإدارة المالية',
        'إدارة الإنتاج',
        'إدارة التخطيط',
      ],
      employeeNameList: ['Employee1', 'Employee3', 'Employee4', 'Employee5'],
    }
  },
}
</script>
<style scoped lang="scss"></style>
