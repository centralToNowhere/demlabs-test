<template lang="pug">
  -
    const certificates = [
      "core-t.0",
      "core-t.1",
      "core-t.2",
      "test.test.1",
      "test.test.2",
      "test.test.3",
      "test.test.4",
      "test.test.5",
      "test.test.6",
      "test.test.7"
    ]

  SectionLayout
    template(v-slot:content-header)
      span Certificates
    template(v-slot:content-list)
      span.content__main-title Public
      ul.content__main-list
        each name in certificates
          li.content__main-item= name
    template(v-slot:content-controls)
</template>

<script>
import Vue from 'vue'
import SectionLayout from '~/layouts/section'

export default Vue.extend({
  name: 'Certificates',
  components: {
    SectionLayout,
  },
})
</script>
