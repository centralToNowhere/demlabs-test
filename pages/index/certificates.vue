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
      Settings(settings-title="Filter")
        template(v-slot:settings-container)
          Radio(
            class="certificates-page__radio"
            radio-title="Public certificates"
            radio-name="cert-filter"
            radio-value="1"
          )
          Radio(
            class="certificates-page__radio"
            radio-title="Private certificates"
            radio-name="cert-filter"
            radio-value="2"
          )
          Radio(
            class="certificates-page__radio"
            radio-title="Both"
            radio-name="cert-filter"
            radio-value="3"
          )

      Settings(settings-title="Actions")
        template(v-slot:settings-container)
          ButtonComponent(
            class="certificates-page__button"
            button-title="Create certificate"
            button-size="large"
          )
          ButtonComponent(
            class="certificates-page__button"
            button-title="Import  certificate"
            button-size="large"
          )
          ButtonComponent(
            class="certificates-page__button"
            button-title="Export private certificate to public"
            button-size="large"
            button-disabled=true
          )
          ButtonComponent(
            class="certificates-page__button"
            button-title="Export certificate to mempool"
            button-size="large"
            button-disabled=true
          )
          ButtonComponent(
            class="certificates-page__button"
            button-title="Delete certificate"
            button-size="large"
            button-disabled=true
          )
</template>

<script>
import Vue from 'vue'
import SectionLayout from '~/layouts/section'
import Settings from '~/components/settings'
import Radio from '~/components/radio'
import ButtonComponent from '~/components/button'

export default Vue.extend({
  name: 'Certificates',
  components: {
    SectionLayout,
    Settings,
    Radio,
    ButtonComponent,
  },
})
</script>

<style lang="scss">
@use '~style/functions' as fn;

.certificates-page {
  &__radio {
    margin-bottom: fn.pxToRem(32);
  }

  &__button {
    margin-bottom: fn.pxToRem(20);
  }
}
</style>
