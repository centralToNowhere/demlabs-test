<template lang="pug">
  header
</template>

<style lang="scss">
@use '~style/functions' as fn;
@use '~style/mixins' as mx;

header {
  display: flex;
  height: fn.pxToRem(60);
  margin-left: fn.pxToRem(3);
  border-bottom-left-radius: fn.pxToRem(15);

  @include mx.themify() using ($p) {
    background-color: fn.color('surface', $p);
    box-shadow: inset 1px 1px fn.color('shadow4', $p),
      5px 5px 10px fn.color('shadow2', $p);
    border-left: 1px solid fn.color('secondary', $p);
    border-top: 1px solid fn.color('secondary', $p);
  }
}
</style>
