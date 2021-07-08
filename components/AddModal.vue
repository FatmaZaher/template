<template>
  <b-modal id="InviteUserModal" v-model="isVisible" size="lg" hide-footer>
    <template #modal-title>
      <span>{{ modalTitle }}</span>
    </template>
    <form ref="form" @submit.stop.prevent="">
      <b-row>
        <b-col md="6" v-if="isEmployeeNo">
          <b-form-group
            label="رقم الموظف"
            label-for="employeeNo"
            invalid-feedback="Employee No. is required"
          >
            <b-form-input id="employeeNo" required></b-form-input>
          </b-form-group>
        </b-col>
        <b-col md="6" v-if="isEmployeeName">
          <b-form-group
            label="الإسم"
            label-for="employeeName"
            invalid-feedback="Name is required"
          >
            <b-form-input id="employeeName" required></b-form-input>
          </b-form-group>
        </b-col>
        <b-col md="6" v-if="isEmployeeEmail">
          <b-form-group
            label="البريد الإلكتروني"
            label-for="employeeEmail"
            invalid-feedback="Email is required"
          >
            <b-form-input
              id="employeeEmail"
              type="email"
              required
            ></b-form-input>
          </b-form-group>
        </b-col>
        <b-col md="6" v-if="isSection">
          <b-form-group
            label="القسم"
            label-for="section"
            invalid-feedback="Section is required"
          >
            <v-select dir="rtl" :options="sections"></v-select>
          </b-form-group>
        </b-col>
        <b-col md="6" v-if="isAdministration">
          <b-form-group
            label="الإدارة"
            label-for="administration"
            invalid-feedback="Administration is required"
          >
            <v-select dir="rtl" :options="administrations"></v-select>
          </b-form-group>
        </b-col>
        <b-col md="6" v-if="isJobName">
          <b-form-group
            label="المسمى الوظيفي"
            label-for="jobName"
            invalid-feedback="Job Name is required"
          >
            <b-form-input id="jobName" required></b-form-input>
          </b-form-group>
        </b-col>
        <b-col md="6" v-if="isPersntage">
          <b-form-group
            label="نسبة الإمتثال"
            label-for="CompliancePers"
            invalid-feedback="Persntage is required"
          >
            <b-form-input id="persntage" required></b-form-input>
          </b-form-group>
        </b-col>
        <b-col md="6" v-if="isMobileNo">
          <b-form-group
            label="رقم الهاتف"
            label-for="mobileNo"
            invalid-feedback="Mobile No. is required"
          >
            <b-form-input id="mobileNo" required></b-form-input>
          </b-form-group>
        </b-col>
        <b-col md="6" v-if="isCity">
          <b-form-group
            label="المدينة"
            label-for="city"
            invalid-feedback="City is required"
          >
            <v-select dir="rtl" :options="cites"></v-select>
          </b-form-group>
        </b-col>
        <b-col md="6" v-if="isValidity">
          <b-form-group
            label="الصلاحية"
            label-for="validity"
            invalid-feedback="Validity is required"
          >
            <v-select dir="rtl" :options="validites"></v-select>
          </b-form-group>
        </b-col>
        <b-col md="6" v-if="isAddPhoto">
          <b-form-group label="إضافة صورة">
            <b-form-file
              placeholder="إضافة صورة"
              drop-placeholder="Drop file here..."
            ></b-form-file>
          </b-form-group>
        </b-col>
        <b-col md="6" v-if="isReportCode">
          <b-form-group
            label="رمز التقرير"
            label-for="reportCode"
            invalid-feedback="Report Code is required"
          >
            <b-form-input id="reportCode" required></b-form-input>
          </b-form-group>
        </b-col>
        <b-col md="6" v-if="isReleaseDate">
          <b-form-group
            label="تاريخ الإصدار"
            label-for="releaseDate"
            invalid-feedback="Date is required"
          >
            <b-form-datepicker id="releaseDate"> </b-form-datepicker>
          </b-form-group>
        </b-col>
        <b-col md="6" v-if="isSampelsNo">
          <b-form-group
            label="عدد العينات"
            label-for="samplesNo"
            invalid-feedback="Sampels No. is required"
          >
            <b-form-input id="samplesNo" required></b-form-input>
          </b-form-group>
        </b-col>
        <b-col md="6" v-if="isMonitoringSource">
          <b-form-group
            label="مصدر الرصد"
            label-for="monitoringSource"
            invalid-feedback="Monitoring source is required"
          >
            <b-form-input id="monitoringSource" required></b-form-input>
          </b-form-group>
        </b-col>
        <b-col md="6" v-if="isReportNo">
          <b-form-group
            label="رقم التقرير"
            label-for="reportNo"
            invalid-feedback="Report No. source is required"
          >
            <b-form-input id="reportNo" required></b-form-input>
          </b-form-group>
        </b-col>
        <b-col md="6" v-if="isComplianceCase">
          <b-form-group
            label="حالة الامتثال"
            label-for="complianceCase"
            invalid-feedback="Compliance Case is required"
          >
            <v-select dir="rtl" :options="complianceCases"></v-select>
          </b-form-group>
        </b-col>
        <b-col md="6" v-if="isAction">
          <b-form-group
            label="الإجراء"
            label-for="action"
            invalid-feedback="Action source is required"
          >
            <b-form-input id="action" required></b-form-input>
          </b-form-group>
        </b-col>
        <b-col md="6" v-if="isReportType">
          <b-form-group
            label="نوع التقرير"
            label-for="reportsType"
            invalid-feedback="Report Type is required"
          >
            <v-select dir="rtl" :options="reportsTypes"></v-select>
          </b-form-group>
        </b-col>
        <b-col md="6" v-if="isVerificationCase">
          <b-form-group
            label="حالة التحقق"
            label-for="verificationCase"
            invalid-feedback="Verification Case is required"
          >
            <v-select dir="rtl" :options="verificationCases"></v-select>
          </b-form-group>
        </b-col>
        <b-col md="6" v-if="isCasesCode">
          <b-form-group
            label="رموز الحالات"
            label-for="casesCodes"
            invalid-feedback="Cases Code is required"
          >
            <b-form-input id="casesCodes" required></b-form-input>
          </b-form-group>
        </b-col>
        <b-col md="6" v-if="isActive">
          <b-form-group
            label="النشاط"
            label-for="active"
            invalid-feedback="Active is required"
          >
            <b-form-input id="active" required></b-form-input>
          </b-form-group>
        </b-col>
        <b-col md="6" v-if="isActual">
          <b-form-group
            label="الاحتواء والاجراء الفعلي"
            label-for="actual"
            invalid-feedback="is required"
          >
            <b-form-input id="actual" required></b-form-input>
          </b-form-group>
        </b-col>
        <b-col md="6" v-if="isSampleCode">
          <b-form-group
            label="رمز العينة"
            label-for="sampleCode"
            invalid-feedback="Sample Code is required"
          >
            <b-form-input id="sampleCode" required></b-form-input>
          </b-form-group>
        </b-col>
        <b-col md="6" v-if="isRang">
          <b-form-group
            label="النطاق"
            label-for="rang"
            invalid-feedback="rang is required"
          >
            <b-form-input id="rang" required></b-form-input>
          </b-form-group>
        </b-col>
        <b-col md="6" v-if="isRepetitiveCase">
          <b-form-group
            label="الحالة التكرارية"
            label-for="repetitiveCase"
            invalid-feedback="ٌRepetitive Case is required"
          >
            <b-form-input id="repetitiveCase" required></b-form-input>
          </b-form-group>
        </b-col>
        <b-col md="6" v-if="isMonitoringCase">
          <b-form-group
            label="حالة الرصد"
            label-for="monitoringCase"
            invalid-feedback="Monitoring Case Case is required"
          >
            <v-select dir="rtl" :options="monitoringCases"></v-select>
          </b-form-group>
        </b-col>
        <b-col md="6" v-if="isResponsible1">
          <b-form-group
            label="المسؤولية 1"
            label-for="responsible1"
            invalid-feedback="Responsible1 is required"
          >
            <b-form-input id="responsible1" required></b-form-input>
          </b-form-group>
        </b-col>
        <b-col md="6" v-if="isResponsible2">
          <b-form-group
            label="المسؤولية 2"
            label-for="responsible2"
            invalid-feedback="Responsible2 is required"
          >
            <b-form-input id="responsible2" required></b-form-input>
          </b-form-group>
        </b-col>
        <b-col md="6" v-if="isResponsible3">
          <b-form-group
            label="المسؤولية 3"
            label-for="responsible3"
            invalid-feedback="Responsible3 is required"
          >
            <b-form-input id="responsible3" required></b-form-input>
          </b-form-group>
        </b-col>
        <b-col md="6" v-if="isMonitoringPers">
          <b-form-group
            label="نسبة صحة الرصد"
            label-for="monitoringPers"
            invalid-feedback="monitoringPers is required"
          >
            <b-form-input id="monitoringPers" required></b-form-input>
          </b-form-group>
        </b-col>
        <b-col md="6" v-if="isSampleName">
          <b-form-group
            label="اسم العينة"
            label-for="sampleName"
            invalid-feedback="Sample Name Code is required"
          >
            <b-form-input id="sampleName" required></b-form-input>
          </b-form-group>
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
            <b-row v-if="selected == 1">
              <b-col md="6">
                <b-form-group
                  label="القسم"
                  label-for="section"
                  invalid-feedback="Section is required"
                >
                  <v-select dir="rtl" :options="sections"></v-select>
                </b-form-group>
              </b-col>
              <b-col md="6">
                <b-form-group
                  label="إسم مدير القسم"
                  label-for="managerName"
                  invalid-feedback="Manager is required"
                >
                  <b-form-input id="Manager" required></b-form-input>
                </b-form-group>
              </b-col>
            </b-row>
            <b-row v-if="selected == 2">
              <b-col md="6">
                <b-form-group
                  label="الإدارة"
                  label-for="administration"
                  invalid-feedback="Administration is required"
                >
                  <v-select dir="rtl" :options="administrations"></v-select>
                </b-form-group>
              </b-col>
              <b-col md="6">
                <b-form-group
                  label="إسم مدير الإدارة"
                  label-for="managerName"
                  invalid-feedback="Manager is required"
                >
                  <b-form-input id="Manager" required></b-form-input>
                </b-form-group>
              </b-col>
            </b-row>
          </div>
        </div>
        <div v-if="isDeleteModal" class="text-center w-100">
          <img src="~/assets/images/Group 12868.png" alt="" />
          <p class="mt-3">هل أنت متأكد من عملية الحذف</p>
          <div class="footer-button d-flex justify-content-center">
            <b-button type="" class="fot-btn mx-3">حذف</b-button>
            <b-button type="" class="fot-btn mx-3">إغلاق</b-button>
          </div>
        </div>
      </b-row>

      <div
        v-if="saveButton"
        class="footer-button d-flex justify-content-center"
      >
        <b-button type="submit" class="fot-btn">حفظ</b-button>
      </div>
    </form>
  </b-modal>
</template>

<script>
export default {
  props: {
    openModal: {
      type: Boolean,
      default: true,
    },
    modalTitle: {
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
    isSampelsNo: {
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
    isAction: {
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
    isRang: {
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
  },
  data() {
    return {
      validites: ['validity1', 'validity2', 'validity3', 'validity4'],
      cites: ['city 2', 'city 3', 'city 4', 'city 5', 'city 6', 'city 7'],
      sections: [
        'قسم الشئون الماليه والمحاسبة',
        'قسم الموارد البشرية',
        'قسم الجوده',
        'قسم ادارة المخازن وتوفير المنتج',
      ],
      administrations: [
        'إدارة التسويق',
        'الإدارة المالية',
        'إدارة الإنتاج',
        'إدارة التخطيط',
      ],
      complianceCases: ['ممتثل', 'غير ممتثل'],
      reportsTypes: ['إحصائي', 'مالي', 'إداري', 'تحليلي'],
      verificationCases: ['لم يتم التحقق بعد', 'جاري التحقق', 'تم التحقق'],
      monitoringCases: ['صحيحة', 'خاطئة'],
      selected: 1,
      radioOptions: [
        { item: 1, name: 'قسم' },
        { item: 2, name: 'إدارة' },
      ],
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
}
</script>
