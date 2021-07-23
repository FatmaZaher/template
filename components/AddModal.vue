<template>
  <b-modal id="InviteUserModal" v-model="isVisible" size="lg" hide-footer>
    <template #modal-title>
      <span>{{ buttonTitle }}</span>
    </template>
    <b-form ref="form" @submit.stop.prevent="">
      <b-row>
        <b-col md="6" v-if="isEmployeeNo">
          <Input
            labelfor="employeeNo"
            labelname="الرقم الوظيفي"
            typeinput="number"
          />
        </b-col>
        <b-col md="6" v-if="isEmployeeName">
          <Input
            labelfor="employeeName"
            labelname="إسم الموظف"
            typeinput="text"
          />
        </b-col>
        <b-col md="6" v-if="isEmployeeEmail">
          <Input
            labelfor="employeeEmail"
            labelname="البريد الإلكتروني"
            typeinput="email"
          />
        </b-col>
        <b-col md="6" v-if="isSection">
          <VSelectInput
            labelfor="section"
            label="القسم"
            :options="sectionList"
          />
        </b-col>
        <b-col md="6" v-if="isReportNo">
          <Input
            labelfor="reportNo"
            labelname="رقم التقرير"
            typeinput="number"
          />
        </b-col>
        <b-col md="6" v-if="isReportCode">
          <Input
            labelfor="reportCode"
            labelname="رمز التقرير"
            typeinput="text"
          />
        </b-col>
        <b-col md="6" v-if="isSampleName">
          <Input
            labelfor="sampleName"
            labelname="اسم العينة"
            typeinput="text"
          />
        </b-col>
        <b-col md="6" v-if="isSampleCodeSelect">
          <VSelectInput
            labelfor="sampleCode"
            label="رمز العينة "
            :options="sampleCodeList"
          />
        </b-col>
        <b-col md="6" v-if="isSampleCode">
          <Input
            labelfor="sampleCode"
            labelname="رمز العينة"
            typeinput="text"
          />
        </b-col>
        <b-col md="6" v-if="isAdministration">
          <VSelectInput
            labelfor="administration"
            label="الإدارة"
            :options="administrationList"
          />
        </b-col>
        <b-col md="6" v-if="isJobName">
          <Input
            labelfor="jobName"
            labelname="المسمى الوظيفي"
            typeinput="text"
          />
        </b-col>
        <b-col md="6" v-if="isPersntage">
          <Input
            labelfor="compliancePers"
            labelname="نسبة الإمتثال"
            typeinput="text"
          />
        </b-col>
        <b-col md="6" v-if="isMobileNo">
          <Input
            labelfor="mobileNo"
            labelname="رقم الهاتف"
            typeinput="number"
          />
        </b-col>
        <b-col md="6" v-if="isCity">
          <VSelectInput labelfor="city" label="المدينة" :options="cityList" />
        </b-col>
        <b-col md="6" v-if="isValidity">
          <VSelectInput
            labelfor="validity"
            label="الصلاحية"
            :options="validityList"
          />
        </b-col>
        <b-col md="6" offset-md="3" v-if="isAddPhoto">
          <FormFile labelfor="File" labelname="إضافة صورة" />
        </b-col>

        <b-col md="6" v-if="isReleaseDate">
          <DatepickerInput labelfor="releaseDate" labelname="تاريخ الإصدار" />
        </b-col>
        <b-col md="6" v-if="isCheckPoint">
          <VSelectInput
            labelfor="checkpoint"
            label="نقطة التحقق"
            :options="checkpointList"
          />
        </b-col>
        <b-col md="6" v-if="isSamplesNo">
          <Input
            labelfor="samplesNo"
            labelname="عدد العينات"
            typeinput="number"
          />
        </b-col>
        <b-col md="6" v-if="isMonitoringSource">
          <VSelectInput
            labelfor="monitoringSource"
            label="مصدر الرصد"
            :options="monitoringSourceList"
          />
        </b-col>

        <b-col md="6" v-if="isComplianceCase">
          <VSelectInput
            labelfor="complianceCase"
            label="حالة الامتثال"
            :options="complianceCaseList"
          />
        </b-col>
        <b-col md="6" v-if="isActionName">
          <VSelectInput
            labelfor="actionName"
            label="إسم الإجراء"
            :options="actionList"
          />
        </b-col>
        <b-col md="6" v-if="isReportType">
          <VSelectInput
            labelfor="reportsType"
            label="نوع التقرير"
            :options="reportsTypeList"
          />
        </b-col>
        <b-col md="6" v-if="isVerificationCase">
          <VSelectInput
            labelfor="verificationCase"
            label="حالة التحقق"
            :options="verificationCaseList"
          />
        </b-col>
        <b-col md="6" v-if="isCasesCode">
          <Input
            labelfor="casesCodes"
            labelname="رموز الحالات"
            typeinput="text"
          />
        </b-col>
        <b-col md="6" v-if="isActive">
          <Input labelfor="active" labelname="النشاط" typeinput="text" />
        </b-col>
        <b-col md="6" v-if="isActual">
          <Input
            labelfor="actual"
            labelname="الاحتواء والاجراء الفعلي"
            typeinput="text"
          />
        </b-col>

        <b-col md="6" v-if="isRangName">
          <VSelectInput
            labelfor="rangName"
            label="اسم النطاق"
            :options="rangLsit"
          />
        </b-col>
        <b-col md="6" v-if="isRepetitiveCase">
          <Input
            labelfor="repetitiveCase"
            labelname="الحالة التكرارية"
            typeinput="number"
          />
        </b-col>
        <b-col md="6" v-if="isMonitoringCase">
          <VSelectInput
            labelfor="monitoringCase"
            label="حالة الرصد"
            :options="monitoringCaseList"
          />
        </b-col>
        <b-col md="6" v-if="isResponsible">
          <Input
            labelfor="responsible"
            labelname="المسؤولية"
            typeinput="text"
          />
        </b-col>
        <b-col md="6" v-if="isResponsible1">
          <Input
            labelfor="responsible1"
            labelname="المسؤولية 1"
            typeinput="text"
          />
        </b-col>
        <b-col md="6" v-if="isResponsible2">
          <Input
            labelfor="responsible2"
            labelname="المسؤولية 2"
            typeinput="text"
          />
        </b-col>
        <b-col md="6" v-if="isResponsible3">
          <Input
            labelfor="responsible3"
            labelname="المسؤولية 3"
            typeinput="text"
          />
        </b-col>
        <b-col md="6" v-if="isMonitoringPers">
          <Input
            labelfor="monitoringPers"
            labelname="نسبة صحة الرصد"
            typeinput="text"
          />
        </b-col>

        <div v-if="isSectionModal" class="sectionForm">
          <b-form-radio-group
            v-model="selected"
            :options="radioOptions"
            class="d-flex justify-content-center"
            value-field="item"
            text-field="name"
            disabled-field="notEnabled"
          ></b-form-radio-group>
          <div class="mt-5">
            <div v-if="selected == 1">
              <Input
                labelfor="section"
                labelname="القسم (الوكالة)"
                typeinput="text"
              />
              <VSelectInput
                labelfor="sectionManagerName"
                label="إسم مدير القسم"
                :options="employeeNameList"
              />
              <VSelectInput
                labelfor="administration"
                label="إسم الإدارة التي يندرج تحتها القسم"
                :options="administrationList"
              />
            </div>
            <div v-if="selected == 2">
              <Input
                labelfor="administration"
                labelname="الإدارة"
                typeinput="text"
              />
              <VSelectInput
                labelfor="adminManagerName"
                label="إسم مدير الإدارة"
                v-modal="kkkk"
                :options="employeeNameList"
              />
            </div>
          </div>
        </div>
        <div v-if="isDeleteModal" class="text-center w-100">
          <img src="~/assets/images/Group 12868.png" alt="delete img" />
          <p class="my-4">{{ deleteText }}</p>
          <div class="footer-button d-flex justify-content-center">
            <b-button type="" class="fot-btn main-btn mx-3">حذف</b-button>
            <b-button type="" class="fot-btn main-btn mx-3 close-btn"
              >إغلاق</b-button
            >
          </div>
        </div>
        <div v-if="compareAndCheck" class="text-center w-100">
          <img src="~/assets/images/Group 12821.png" alt="delete img" />
          <p class="my-4">تمت عملية التحقق بنجاح وتحديد الحالة</p>
          <div class="footer-button">
            <b-button type="" class="fot-btn main-btn mx-3">ممتثل</b-button>
            <b-button type="" class="fot-btn main-btn mx-3 close-btn"
              >إغلاق</b-button
            >
          </div>
        </div>
      </b-row>
      <div
        v-if="saveButton"
        class="footer-button d-flex justify-content-center"
      >
        <b-button type="submit" class="fot-btn main-btn">حفظ</b-button>
      </div>
    </b-form>
  </b-modal>
</template>

<script>
export default {
  props: {
    openModal: {
      type: Boolean,
      default: true,
    },
    buttonTitle: {
      type: null,
      default: '',
    },
    value: {
      type: null,
      default: '',
    },
    isEmployeeNo: {
      type: Boolean,
      default: false,
    },
    isEmployeeName: {
      type: Boolean,
      default: false,
    },
    isEmployeeEmail: {
      type: Boolean,
      default: false,
    },
    isCheckPoint: {
      type: Boolean,
      default: false,
    },
    isSection: {
      type: Boolean,
      default: false,
    },
    isCity: {
      type: Boolean,
      default: false,
    },
    isAdministration: {
      type: Boolean,
      default: false,
    },
    isJobName: {
      type: Boolean,
      default: false,
    },
    isPersntage: {
      type: Boolean,
      default: false,
    },
    isMobileNo: {
      type: Boolean,
      default: false,
    },
    isValidity: {
      type: Boolean,
      default: false,
    },
    isAddPhoto: {
      type: Boolean,
      default: false,
    },
    isReportCode: {
      type: Boolean,
      default: false,
    },
    isReleaseDate: {
      type: Boolean,
      default: false,
    },
    isSamplesNo: {
      type: Boolean,
      default: false,
    },
    isMonitoringSource: {
      type: Boolean,
      default: false,
    },
    isReportNo: {
      type: Boolean,
      default: false,
    },
    isComplianceCase: {
      type: Boolean,
      default: false,
    },
    isActionName: {
      type: Boolean,
      default: false,
    },
    isReportType: {
      type: Boolean,
      default: false,
    },
    isVerificationCase: {
      type: Boolean,
      default: false,
    },
    isCasesCode: {
      type: Boolean,
      default: false,
    },
    isActive: {
      type: Boolean,
      default: false,
    },
    isActual: {
      type: Boolean,
      default: false,
    },
    isSampleCode: {
      type: Boolean,
      default: false,
    },
    isSampleCodeSelect: {
      type: Boolean,
      default: false,
    },
    isRangName: {
      type: Boolean,
      default: false,
    },
    isRangCode: {
      type: Boolean,
      default: false,
    },
    isRepetitiveCase: {
      type: Boolean,
      default: false,
    },
    isMonitoringCase: {
      type: Boolean,
      default: false,
    },
    isResponsible: {
      type: Boolean,
      default: false,
    },
    isResponsible1: {
      type: Boolean,
      default: false,
    },
    isResponsible2: {
      type: Boolean,
      default: false,
    },
    isResponsible3: {
      type: Boolean,
      default: false,
    },
    isMonitoringPers: {
      type: Boolean,
      default: false,
    },
    isSampleName: {
      type: Boolean,
      default: false,
    },
    isSectionModal: {
      type: Boolean,
      default: false,
    },
    isDeleteModal: {
      type: Boolean,
      default: false,
    },
    saveButton: {
      type: Boolean,
      default: true,
    },
    deleteText: {
      type: String,
      default: '',
    },
    compareAndCheck: {
      type: Boolean,
      default: false,
    },
  },
  data() {
    return {
      selected: 1,
      validityList: ['validity1', 'validity2', 'validity3', 'validity4'],
      cityList: ['city 2', 'city 3', 'city 4', 'city 5', 'city 6', 'city 7'],
      sectionList: [
        'قسم الشئون الماليه والمحاسبة',
        'قسم الموارد البشرية',
        'قسم الجوده',
        'قسم ادارة المخازن وتوفير المنتج',
      ],
      administrationList: [
        'إدارة التسويق',
        'الإدارة المالية',
        'إدارة الإنتاج',
        'إدارة التخطيط',
      ],
      complianceCaseList: ['ممتثل', 'غير ممتثل'],
      reportsTypeList: ['إحصائي', 'مالي', 'إداري', 'تحليلي'],
      verificationCaseList: ['لم يتم التحقق بعد', 'جاري التحقق', 'تم التحقق'],
      monitoringCaseList: ['صحيحة', 'خاطئة'],
      radioOptions: [
        { item: 1, name: 'قسم' },
        { item: 2, name: 'إدارة' },
      ],
      employeeNameList: ['Employee1', 'Employee3', 'Employee4', 'Employee5'],
      checkpointList: ['checkpoint 2', 'checkpoint 3', 'checkpoint 4'],
      monitoringSourceList: [
        'Source 2',
        'Source 3',
        'Source 4',
        'Source 5',
        'Source 6',
        'Source 7',
      ],
      actionList: ['action 2', 'action 3', 'action 4'],
      rangLsit: ['داخل نطاق الرقابة والحوكمة', 'خارج نطاق الجودة والحوكمة'],
      sampleCodeList: ['samples 2', 'samples 3', 'samples 4'],
    }
  },
  computed: {
    isVisible: {
      get() {
        return this.value
      },
      set(val) {
        this.$emit('input', val)
      },
    },
  },
  methods: {
    closeModal() {
      this.openmodal = false
    },
  },
}
</script>
