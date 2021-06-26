<template>
  <div class="page-content">
    <Header />
    <PageContent />
  </div>
</template>

<script>
import Header from '~/components/Header.vue'
import PageContent from '~/components/PageContent.vue'

export default {
  components: {
    Header,
    PageContent
  },
}
</script>

<style></style>
