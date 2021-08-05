<template>
  <div>
    <Header
      :title="title"
      :subHeader="true"
      subHeaderlink="/Monitoring/MonitoringSources"
      :subHeaderTitle="subHeaderTitle"
    />
    <div class="content subpage">
      <div class="text-center mt-4">
        <h5>{{ title }}</h5>
      </div>
      <b-form ref="form" @submit.stop.prevent="">
        <b-row>
          <b-col cols="12">
            <Input
              labelfor="sourceCode"
              labelname="رمز المصدر"
              typeinput="text"
              icon="CodesIcon"
            />
          </b-col>
          <b-col cols="12">
            <Input
              labelfor="monitoringSource"
              labelname="مصدر الرصد"
              typeinput="text"
              icon="SourceIcon"
            />
          </b-col>
          <b-col cols="12">
          <div class="footer-button d-flex justify-content-between">
            <b-button type="submit" class="fot-btn main-btn w-100 mt-3 mr-3"
              >حفظ</b-button
            >
            <b-button type="" class="fot-btn main-btn w-100 mt-3 close-btn"
              >إلغاء</b-button
            >
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
      title: 'إضافة مصدر رصد',
      subHeaderTitle:'مصادر الرصد',
    }
  },
}
</script>
<style scoped lang="scss"></style>
