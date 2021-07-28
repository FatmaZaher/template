<template>
  <b-modal id="InviteUserModal" v-model="isVisible" :size="size" hide-footer>
    <template #modal-title>
      <span>{{ buttonTitle }}</span>
    </template>
    <b-form ref="form" @submit.stop.prevent="">
      <b-row>
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
        <b-col v-if="isActual">
          <Input
            labelfor="actual"
            labelname="الاحتواء والاجراء الفعلي"
            typeinput="text"
          />
        </b-col>
        <b-col v-if="isQualityNotes">
          <Textarea
            labelfor="qualityManagerNotes"
            labelname="ملاحظات مدير الجودة"
          />
        </b-col>
        <b-col v-if="isStakeholderNotes">
          <Textarea
            labelfor="stakeholderNotes"
            labelname="ملاحظات الجهة المعنية"
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
        <b-col md="6" v-if="isMonitoringCaseSelect">
          <VSelectInput
            labelfor="monitoringCase"
            label="حالة الرصد"
            :options="monitoringCaseList"
          />
        </b-col>
        <b-col md="6" v-if="isMonitoringStatusCode">
          <Input
            labelfor="monitoringStatusCode"
            labelname="رمز حالة الرصد"
            typeinput="text"
          />
        </b-col>
        <b-col md="6" v-if="isMonitoringCase">
          <Input
            labelfor="monitoringCase"
            labelname="حالة الرصد"
            typeinput="text"
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
        <b-col md="6" v-if="isCompliancePers">
          <Input
            labelfor="compliancePers"
            labelname="نسبة الإمتثال"
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
          <div class="iconModal my-2" style="backgroundColor: var(--red-color) !important" >
            <TrashIcon class="icon"/>
          </div>
          <p class="my-4">{{ deleteText }}</p>
          <div class="footer-button d-flex justify-content-center">
            <b-button type="" class="fot-btn main-btn mr-3">حذف</b-button>
            <b-button type="" class="fot-btn main-btn close-btn"
              >إغلاق</b-button
            >
          </div>
        </div>
        <div v-if="compareAndCheck" class="text-center w-100">
          <div class="iconModal">
            <CheckIcon class="icon" />
          </div>
          <p class="my-4">تمت عملية التحقق بنجاح وتحديد الحالة</p>
          <div class="footer-button">
            <b-button type="" class="fot-btn main-btn mr-3">ممتثل</b-button>
            <b-button type="" class="fot-btn main-btn close-btn"
              >إغلاق</b-button
            >
          </div>
        </div>
        <div v-if="complianceRecord" class="text-center w-100">
          <div class="mb-4">
            <EditIcon />
            <span class="ml-1">تعديل إمتثال الإدارة</span>
          </div>
          <Input
            labelfor="administration"
            labelname="الإدارة"
            typeinput="text"
          />
          <Input
            labelfor="compliancePers"
            labelname="نسبة الإمتثال"
            typeinput="text"
          />
          <div class="footer-button">
            <b-button
              type=""
              @click="editConfirmModal"
              class="fot-btn main-btn mr-3"
              >حفظ
              <b-modal v-model="editconfirmmodal" hide-footer>
                <div class="mb-4 text-center">
                  <div>تعديل الحالة</div>
                  <div class="iconModal my-4">
                    <EditIcon class="icon" />
                  </div>
                  <div>هل تقبل تعديل حالة الإمتثال؟</div>
                </div>
                <div class="footer-button d-flex justify-content-center">
                  <b-button type="" class="fot-btn main-btn mr-3"
                    >تأكيد</b-button
                  >
                  <b-button type="" class="fot-btn main-btn close-btn"
                    >إغلاق</b-button
                  >
                </div>
              </b-modal>
            </b-button>
            <b-button type="" class="fot-btn main-btn close-btn"
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
    size: {
      type: String,
      default: 'lg',
    },
    buttonTitle: {
      type: null,
      default: '',
    },
    value: {
      type: null,
      default: '',
    },
    isCheckPoint: {
      type: Boolean,
      default: false,
    },
    isAdministration: {
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
    isQualityNotes: {
      type: Boolean,
      default: false,
    },
    isStakeholderNotes: {
      type: Boolean,
      default: false,
    },
    isSampleCode: {
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
    isMonitoringCaseSelect: {
      type: Boolean,
      default: false,
    },
    isMonitoringCase: {
      type: Boolean,
      default: false,
    },
    isMonitoringStatusCode: {
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
    isCompliancePers: {
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
    complianceRecord: {
      type: Boolean,
      default: false,
    },
  },
  data() {
    return {
      editconfirmmodal: false,
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
      actionList: ['action 2', 'action 3', 'action 4'],
      rangLsit: ['داخل نطاق الرقابة والحوكمة', 'خارج نطاق الجودة والحوكمة'],
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
    editConfirmModal() {
      this.editconfirmmodal = true
    },
  },
}
</script>
<style lang="scss" scoped>
.iconModal {
  background-color: var(--main-color);
  display: inline-block;
  height: 100px;
  width: 100px;
  border-radius: 100%;
  line-height: 100px;
  .icon {
    width: 30px;
  }
  svg {
    fill: #fff;
  }
}
</style>
