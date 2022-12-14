<template lang="pug">
  header.header
    SearchComponent
    .header__right-container
      ThemeToggle
</template>

<script lang="ts">
import { defineComponent } from 'vue'
import SearchComponent from '@/components/search/index.vue'
import ThemeToggle from '@/components/themeToggle/index.vue'

export default defineComponent({
  name: 'HeaderComponent',
  components: {
    SearchComponent,
    ThemeToggle,
  },
})
</script>

<style lang="scss">
@use '~style/functions' as fn;
@use '~style/mixins' as mx;

.header {
  display: flex;
  height: fn.pxToRem(60);
  margin-left: fn.pxToRem(3);
  border-bottom-left-radius: fn.pxToRem(15);
  padding: fn.pxToRem(14) fn.pxToRem(36) fn.pxToRem(15) fn.pxToRem(36);
  transition: background-color 0.5s linear 0s;

  @include mx.themify() using ($p) {
    background-color: fn.color('surface', $p);
    box-shadow: inset 1px 1px fn.color('shadow4', $p),
      5px 5px 10px fn.color('shadow2', $p);
    border-left: 1px solid fn.color('secondary', $p);
    border-top: 1px solid fn.color('secondary', $p);
  }

  &__right-container {
    display: flex;
    align-items: center;
    justify-content: center;
    margin-left: auto;
  }
}
</style>
