<template lang="pug">
  aside.sidebar
    SidebarLogo
    SidebarNav
</template>

<style lang="scss">
@use '~style/functions' as fn;
@use '~style/mixins' as mx;

.sidebar {
  width: fn.pxToRem(180);
  border-bottom-right-radius: fn.pxToRem(20);

  @include mx.themify() using ($p) {
    box-shadow: 5px 5px 10px fn.color('shadow2', $p),
      inset 1px 1px fn.color('shadow4', $p);
    border-left: 1px solid fn.color('secondary', $p);
    border-top: 1px solid fn.color('secondary', $p);
  }
}
</style>
