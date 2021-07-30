<template>
  <div>
    <Header :title="title" :subHeader="true" subHeaderlink="/Reports" :subHeaderTitle="subHeaderTitle"/>
    <div class="content subpage">
      <div class="text-center mt-4">
        <p>يرجى إدخال جميع بيانات التقرير كاملة</p>
      </div>
      <b-form ref="form" @submit.stop.prevent="">
        <b-row>
          <b-col md="4">
            <Input
              labelfor="reportNo"
              labelname="رقم التقرير"
              typeinput="number"
              icon="ListIcon"
            />
          </b-col>
          <b-col md="4">
            <Input
              labelfor="reportCode"
              labelname="رمز التقرير"
              typeinput="text"
              icon="CodesIcon"
            />
          </b-col>
          <b-col md="4">
            <DatepickerInput labelfor="releaseDate" labelname="تاريخ الإصدار" />
          </b-col>
          <b-col md="4">
            <VSelectInput
              labelfor="caseCode"
              label="رمز الحالة"
              :options="caseCodeList"
              icon="CodesIcon"
            />
          </b-col>
          <b-col md="4">
            <Input
              labelfor="sampleCode"
              labelname="رمز العينة"
              typeinput="text"
              icon="CodesIcon"
            />
          </b-col>
          <b-col md="4">
            <Input
              labelfor="sampleName"
              labelname="اسم العينة"
              typeinput="text"
              icon="FileCodeIcon"
            />
          </b-col>
          <b-col md="4">
            <VSelectInput
              labelfor="administration"
              label="الإدارة"
              :options="administrationList"
              icon="AdminIcon"
            />
          </b-col>
          <b-col md="4">
            <VSelectInput
              labelfor="adminManager"
              label="مدير الإدارة"
              :options="employeeNameList"
              icon="UserIcon"
            />
          </b-col>
          <b-col md="4">
            <VSelectInput
              labelfor="monitoringSource"
              label="مصدر الرصد"
              :options="monitoringSourceList"
              icon="SourceIcon"
            />
          </b-col>
          <b-col md="4">
            <VSelectInput
              labelfor="statusName"
              label="اسم الحالة"
              :options="statusNameList"
              icon="FileIcon"
            />
          </b-col>
          <b-col md="4">
            <Input
              labelfor="repetitiveCase"
              labelname="التكرارية"
              typeinput="number"
              icon="RepeatIcon"
            />
          </b-col>
          <b-col md="4">
            <Input
              labelfor="active"
              labelname="النشاط"
              typeinput="text"
              icon="ActiveIcon"
            />
          </b-col>
          <b-col md="4">
            <VSelectInput
              labelfor="sampleCode"
              label="إضافة رمز عينة سابقة"
              :options="sampleCodeList"
              icon="CodesIcon"
            />
          </b-col>
          <b-col md="4">
            <VSelectInput
              labelfor="verificationResult"
              label="نتيحة التحقق"
              :options="verificationResultList"
              icon="CheckIcon"
            />
          </b-col>
          <b-col md="4">
            <VSelectInput
              labelfor="rang"
              label="اسم النطاق"
              :options="rangLsit"
              icon="RangIcon"
            />
          </b-col>
          <b-col md="4">
            <Input
              labelfor="actual"
              labelname="الاحتواء والاجراء الفوري"
              typeinput="text"
              icon="CheckIcon"
            />
          </b-col>
          <b-col md="4">
            <VSelectInput
              labelfor="monitoringHealth"
              label="هل الرصد صحيح بحسب المبررات؟"
              :options="monitoringHealthList"
              icon="TorFIcon"
            />
          </b-col>
          <b-col md="4">
            <DatepickerInput
              labelfor="correciveDate"
              labelname="تاريخ الإجراء التصحيحي"
            />
          </b-col>
          <b-col md="6">
            <Textarea
              labelfor="qualityManagerNotes"
              labelname="ملاحظات مدير الجودة"
            />
          </b-col>
          <b-col md="6">
            <Textarea
              labelfor="stakeholderNotes"
              labelname="ملاحظات الجهة المعنية"
            />
          </b-col>
          <b-col cols="12">
            <Input
              labelfor="responsible1"
              labelname="المسؤولية 1"
              typeinput="text"
              icon="FileCodeIcon"
            />
          </b-col>
          <b-col cols="12">
            <Input
              labelfor="responsible2"
              labelname="المسؤولية 2"
              typeinput="text"
              icon="FileCodeIcon"
            />
          </b-col>
          <b-col cols="12">
            <Input
              labelfor="responsible3"
              labelname="المسؤولية 3"
              typeinput="text"
              icon="FileCodeIcon"
            />
          </b-col>
          <b-col md="6" offset-sm="3">
            <div class="footer-button d-flex justify-content-center">
              <b-button type="submit" class="fot-btn main-btn w-100">
                إنشاء تقرير
              </b-button>
            </div>
          </b-col>
        </b-row>
      </b-form>
    </div>
  </div>
</template>
<script>
export default {
  data() {
    return {
      title: 'إضافة تقرير',
      subHeaderTitle: 'التقارير',
      monitoringSourceList: ['إدارة الجودةv', 'إدارة المالية'],
      statusNameList: ['status 2', 'status 3', 'status 4'],
      administrationList: [
        'إدارة التسويق',
        'الإدارة المالية',
        'إدارة الإنتاج',
        'إدارة التخطيط',
      ],
      caseCodeList: ['Code 2', 'Code 3', 'Code 4'],
      sampleCodeList: ['samples 2', 'samples 3', 'samples 4'],
      verificationResultList: ['ممتثل', 'غير ممتثل'],
      rangLsit: ['داخل نطاق الرقابة والحوكمة', 'خارج نطاق الجودة والحوكمة'],
      monitoringHealthList: ['نعم', 'لا'],
      employeeNameList: ['Employee1', 'Employee3', 'Employee4', 'Employee5'],
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
