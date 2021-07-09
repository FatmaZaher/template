<template>
  <div class="personal-file">
    <div class="image-side">
      <div class="image">
        <img src="~/assets/images/profile.png" alt="Person image" />
      </div>
      <div class="info">
        <div>
          <h6>
            <i class="fas fa-graduation-cap"></i>
            نسبة الإمتثال
          </h6>
          <span>90 %</span>
        </div>
        <div>
          <h6>
            <i class="far fa-address-card"></i>
            الرقم الوظيفي
          </h6>
          <span>059212121</span>
        </div>
        <div>
          <h6>
            <i class="fas fa-mobile-alt"></i>
            رقم الجوال
          </h6>
          <span>059261548</span>
        </div>
        <div>
          <h6>
            <i class="fas fa-at"></i>
            البريد الإلكتروني
          </h6>
          <span>fatma@gmail.com</span>
        </div>
      </div>
    </div>
    <div class="left-side">
      <div class="left-header">
        <h5>
          <i class="far fa-user"></i>
          محمد أحمد حسين محمد
        </h5>
        <p>
          <i class="fas fa-globe"></i>
          مدير قسم التسويق
        </p>
      </div>
      <div class="table-left-side">
        <b-table
          :items="info"
          thead-class="hidden_header"
          :fields="infofield"
        ></b-table>
      </div>
      <div class="tab_section">
        <h6>تفاصيل العينات</h6>
        <b-tabs class="mt-3">
          <b-tab title="العينات الممثلة" active>
            <div class="table-left-side">
              <TableList :items="samples" :fields="samplefield" :rows="rows" />
            </div>
          </b-tab>
          <b-tab title="العينات الفير ممثلة">
            <TableList :items="samples" :fields="samplefield" :rows="rows" />
          </b-tab>
          <b-tab title="الجميع">
            <TableList :items="samples" :fields="samplefield" :rows="rows" />
          </b-tab>
        </b-tabs>
      </div>
    </div>
  </div>
</template>
<script>
export default {
  data() {
    return {
      title: 'الملف الشخصي',
      infofield: ['sub', 'info'],
      info: [
        { sub: 'رقم التسجيل', info: 2134578 },
        { sub: 'الجنسية', info: 'سعودي' },
        { sub: 'الوكالة', info: 'الإدارة والتوريد' },
        { sub: 'الإدارة', info: 'المالية' },
        { sub: 'نسبة الإمتثال', info: '80%' },
        { sub: 'عدد التقارير', info: '12 تقرير' },
      ],
      samplefield: [
        {
          key: 'sampleName',
          label: 'إسم العينة',
        },
        {
          key: 'sampleCode',
          label: 'رمز العينة',
        },
        {
          key: 'sampleDate',
          label: 'تاريخ العينة',
        },
        {
          key: 'noSample',
          label: 'سبب عدم الإمتثال',
        },
        {
          key: 'CompliancePers',
          label: 'نسبة الإمتثال',
        },
      ],
      samples: [
        {
          sampleName: 'sdd',
          sampleCode: 'dfdf',
          sampleDate: 'dfdf',
          noSample: 'dfdf',
          CompliancePers: 'dfdf',
        },
      ],
    }
  },
  computed: {
    rows() {
      return this.samples.length
    },
  },
}
</script>
<style lang="scss"></style>
