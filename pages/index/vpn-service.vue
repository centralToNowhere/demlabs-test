<template lang="pug">
  - const sectionName = "VPN service";

  SectionLayout
    template(v-slot:content-header)
      span= sectionName
</template>

<script>
import Vue from 'vue'
import SectionLayout from '@/layouts/section.vue'

export default Vue.extend({
  name: 'VPNService',
  components: {
    SectionLayout,
  },
})
</script>
