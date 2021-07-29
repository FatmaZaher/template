<template>
  <div class="content subpage">
    <div class="text-center mt-4">
      <h5>{{ title }}</h5>
    </div>
    <b-form ref="form" @submit.stop.prevent="">
      <Input 
        labelfor="rangCode" 
        labelname="رمز النطاق" 
        typeinput="text" 
      />
      <Input
        labelfor="rangName"
        labelname="اسم النطاق"
         typeinput="text" 
      />
      <FormFile 
        labelfor="ٌRangFile" 
        labelname="إدخال نطاقات من ملف" 
        accept=".doc, .docx, .pdf"
        />

      <div class="footer-button d-flex justify-content-between">
        <b-button type="submit" class="fot-btn main-btn w-100 mt-3 mr-3"
          >حفظ</b-button
        >
        <b-button type="" class="fot-btn main-btn w-100 mt-3 close-btn"
          >إغلاق</b-button
        >
      </div>
    </b-form>
  </div>
</template>

<script>
export default {
  data() {
    return {
      title: 'إضافة نطاق',
    }
  },
}
</script>
<style scoped lang="scss"></style>
