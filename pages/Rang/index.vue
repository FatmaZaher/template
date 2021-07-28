<template>
  <div class="content">
    <div class="header-content">
      <b-row class="align-items-center">
        <b-col cols="6">
          <HeadPage :title="title"></HeadPage>
        </b-col>
        <b-col cols="6">
          <div class="d-flex justify-content-end">
            <b-button class="btn main-btn">
              <nuxt-link :to="'/Rang/AddRang'">
                  <PlusIcon />
                <span class="ml-1"> {{ buttonTitle }}</span>
              </nuxt-link>
            </b-button>
          </div>
        </b-col>
      </b-row>
    </div>
    <TableList
      :items="items"
      :rows="rows"
      :fields="fields"
      :is-edit="true"
      :is-delete="true"
    />
  </div>
</template>

<script>
export default {
  data() {
    return {
      title: 'النطاقات',
      buttonTitle: 'إضافة نطاق ',
      fields: [
        {
          key: 'randCode',
          label: 'رمز النطاق',
        },
        {
          key: 'rangNama',
          label: 'اسم النطاق',
        },
        {
          key: 'id',
          label: '',
        },
      ],
      items: [
        {
          randCode: '011',
          rangNama: 'داخل نطاق الرقابة والحوكمة',
          id: 11,
        },
      ],
    }
  },
  computed: {
    rows() {
      return this.items.length
    },
  },
}
</script>

<style lang="scss"></style>

