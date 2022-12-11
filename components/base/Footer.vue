<template lang="pug">
  footer
</template>

<style lang="scss">
@use '~style/functions' as fn;
@use '~style/mixins' as mx;

footer {
  display: flex;
  height: fn.pxToRem(42);
  margin-top: fn.pxToRem(5);

  @include mx.themify() using ($p) {
    background-color: fn.color('surface', $p);
    box-shadow: 5px -5px 10px fn.color('shadow2', $p),
      inset 1px 1px fn.color('shadow4', $p);
    border-left: 1px solid fn.color('secondary', $p);
    border-top: 1px solid fn.color('secondary', $p);
  }
}
</style>
