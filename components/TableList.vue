<template>
  <div class="table-list">
    <b-table
      responsive
      :items="items"
      small
      id="table-list"
      :per-page="perPage"
      :current-page="currentPage"
    ></b-table>
    <div class="pagin d-flex justify-content-center">
      <b-pagination
        v-model="currentPage"
        :total-rows="rows"
        :per-page="perPage"
        aria-controls="table-list"
      ></b-pagination>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      perPage: 3,
      currentPage: 1,
      items: [
        {
          الإسم: 40,
          الرقم_الوظيفي: 'مثال',
          القسم: 'مثال',
          البريد_الإلكتروني: 'مثال',
          المسمى_الوظيفي: 'مثال',
          الإدارة: 'مثال',
          نسبة_الإمثثال: 'مثال ',
        }
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
