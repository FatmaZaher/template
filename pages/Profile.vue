<template>
  <div>
    <Header :title="title" />
    <div class="personal-file">
      <div class="right-side">
        <div class="image">
          <img src="~/assets/images/profile.png" alt="Person image" />
        </div>
        <div class="info">
          <b-list-group>
            <b-list-group-item
              ><p>
                <GraduateIcon />
                <span class="ml-1"> نسبة الإمتثال</span>
              </p>
              <span>90 %</span></b-list-group-item
            >
            <b-list-group-item
              ><p>
                <CardIcon />
                <span class="ml-1">الرقم الوظيفي</span>
              </p>
              <span>059212121</span>
            </b-list-group-item>
            <b-list-group-item
              ><p>
                <PhoneIcon />
                <span class="ml-1">رقم الجوال</span>
              </p>
              <span>059261548</span>
            </b-list-group-item>
            <b-list-group-item
              ><p>
                <EmailFullIcon />
                <span class="ml-1">البريد الإلكتروني</span>
              </p>
              <span>example@gmail.com</span>
            </b-list-group-item>
          </b-list-group>
        </div>
      </div>
      <div class="left-side">
        <div class="left-header">
          <h5>
            <UserIcon />
            <span class="ml-1">محمد أحمد حسين محمد</span>
          </h5>
          <p>
            <NetworkIcon />
            <span class="ml-1">مدير قسم التسويق</span>
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
                <TableList
                  :items="samples"
                  :fields="samplefield"
                  :rows="rows"
                />
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
          key: 'compliancePers',
          label: 'نسبة الإمتثال',
        },
      ],
      samples: [
        {
          sampleName: 'sdd',
          sampleCode: 'dfdf',
          sampleDate: 'dfdf',
          noSample: 'dfdf',
          compliancePers: 'dfdf',
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
