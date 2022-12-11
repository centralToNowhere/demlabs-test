<template lang="pug">
  -
    const sectionName = "Logs";

  SectionLayout
    template(v-slot:content-header)
      span= sectionName
</template>

<script>
import Vue from 'vue'
import SectionLayout from '~/layouts/section'

export default Vue.extend({
  name: 'Logs',
  components: {
    SectionLayout,
  },
})
</script>
