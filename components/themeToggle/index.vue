<template lang="pug">
  -
    const iconPath = '/icons/theme-toggle.svg'

  .theme-toggle(v-on:click="toggleTheme")
    svg(xmlns="http://www.w3.org/2000/svg" viewBox="0 0 512 512")
      path(d="M448 256c0-106-86-192-192-192V448c106 0 192-86 192-192zm64 0c0 141.4-114.6 256-256 256S0 397.4 0 256S114.6 0 256 0S512 114.6 512 256z")
</template>

<script lang="ts">
import { defineComponent } from 'vue'

export default defineComponent({
  name: 'ThemeToggle',
  methods: {
    toggleTheme: function () {
      const body = document.body
      const classList = body.classList

      classList.toggle('theme-light')
      classList.toggle('theme-dark')
    },
  },
})
</script>

<style lang="scss">
@use '~style/functions' as fn;
@use '~style/mixins' as mx;

.theme-toggle {
  $size: fn.pxToRem(25);
  display: flex;
  justify-content: center;
  align-items: center;
  width: $size;
  height: $size;
  cursor: pointer;

  & path {
    @include mx.themify() using ($p) {
      fill: fn.color('primary', $p);
    }
  }
}
</style>
