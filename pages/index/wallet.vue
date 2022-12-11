<template lang="pug">
  -
    const sectionName = "Wallet";

  SectionLayout
    template(v-slot:content-header)
      span= sectionName
</template>

<script>
import Vue from 'vue'
import SectionLayout from '~/layouts/section'

export default Vue.extend({
  name: 'Wallet',
  components: {
    SectionLayout,
  },
})
</script>
