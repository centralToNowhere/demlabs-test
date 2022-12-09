<template lang="pug">
  footer
</template>

<style lang="scss">
footer {
  display: flex;
  height: fn.pxToRem(42);
  margin-top: fn.pxToRem(5);
  @include mx.prop('background-color', 'surface');
  @include mx.prop('box-shadow', 5px, -5px, 10px, 'shadow2');
  @include mx.prop('border-left', 1px, solid, 'secondary');
  @include mx.prop('border-top', 1px, solid, 'secondary');
}
</style>
