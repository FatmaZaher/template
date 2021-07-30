<template>
  <div>
    <Header
      :title="title"
      :subHeader="true"
      subHeaderlink="/Action"
      :subHeaderTitle="subHeaderTitle"
    />
    <div class="content subpage">
      <div class="text-center mt-4">
        <h5>{{ title }}</h5>
      </div>
      <b-form ref="form" @submit.stop.prevent="">
        <Input
          labelfor="actionNo"
          labelname="رقم الإجراء"
          typeinput="number"
          icon="ListIcon"
        />
        <Input
          labelfor="actionName"
          labelname="إسم الإجراء"
          typeinput="text"
          icon="ActiveIcon"
        />
        <VSelectInput
          labelfor="administration"
          label="الإدارة"
          :options="administrationList"
          icon="AdminIcon"
        />
        <Textarea labelfor="actionText" labelname="نص الإجراء" />
        <div class="footer-button d-flex justify-content-between">
          <b-button type="submit" class="fot-btn main-btn w-100 mt-3 mr-3"
            >حفظ</b-button
          >
          <b-button type="" class="fot-btn main-btn w-100 mt-3 close-btn"
            ><nuxt-link :to="'/Action'"> إلغاء </nuxt-link>
          </b-button>
        </div>
      </b-form>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      title: 'إضافة إجراء',
      subHeaderTitle: 'الإجراءات',
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
