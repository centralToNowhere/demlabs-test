<template lang="pug">
  - const sectionName = "Console";

  SectionLayout
    template(v-slot:content-header)
      span= sectionName
</template>

<script>
import Vue from 'vue'
import SectionLayout from '@/layouts/section.vue'

export default Vue.extend({
  name: 'Console',
  components: {
    SectionLayout,
  },
})
</script>
