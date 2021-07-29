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
              <nuxt-link :to="'/Action/AddAction'">
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
      :is-show="true"
      :is-edit="true"
      :is-delete="true"
    />
  </div>
</template>

<script>
export default {
  data() {
    return {
      title: 'الإجراءات',
      buttonTitle: 'إضافة إجراء ',
      fields: [
        {
          key: 'actionNo',
          label: 'رقم الإجراء',
        },
        {
          key: 'actionName',
          label: 'إسم الإجراء',
        },
        {
          key: 'administration',
          label: 'الإدارة',
        },
        {
          key: 'actionText',
          label: 'نص الإجراء',
        },
        {
          key: 'id',
          label: '',
        },
      ],
      items: [
        {
          actionNo: '00120',
          actionName: '',
          administration: 'إدارة التسويق',
          actionText: '',
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
