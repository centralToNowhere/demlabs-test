<template lang="pug">
  form.settings
    .settings__title {{ settingsTitle}}
    .settings__container
      slot(name="settings-container")
</template>

<script>
import Vue from 'vue'

export default Vue.extend({
  name: 'Settings',
  props: {
    settingsTitle: {
      type: String,
      default: 'Settings',
    },
  },
})
</script>
<style lang="scss">
@use '~style/mixins' as mx;
@use '~style/functions' as fn;

.settings {
  &__title {
    line-height: fn.pxToRem(17.5);

    @include mx.font(14, 'bold');
    @include mx.themify() using ($p) {
      color: fn.color('primary', $p);
    }
  }

  &__container {
    margin: fn.pxToRem(24) 0 fn.pxToRem(8) 0;
  }
}
</style>
