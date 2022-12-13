<template lang="pug">
  .logo
    NuxtImg(src="/images/Logo.svg")
</template>

<style lang="scss">
@use '~style/functions' as fn;
@use '~style/mixins' as mx;

.logo {
  padding: fn.pxToRem(20) 0 fn.pxToRem(20) fn.pxToRem(24);

  @include mx.themify() using ($p) {
    $border-color: fn.color('secondary', $p);
    border-left: 1px solid $border-color;
    border-top: 1px solid $border-color;
    background: fn.color('surface8', $p);
  }
}
</style>
