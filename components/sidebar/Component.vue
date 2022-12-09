<template lang="pug">
  aside.sidebar
    SidebarLogo
    SidebarMenu
</template>

<style lang="scss">
.sidebar {
  width: fn.pxToRem(180);
  border-bottom-right-radius: fn.pxToRem(20);

  @include mx.prop('box-shadow', 5px, 5px, 10px, 'shadow2');
  @include mx.prop('border-left', 1px, solid, 'secondary');
  @include mx.prop('border-top', 1px, solid, 'secondary');
}
</style>
