<template lang="pug">
  header
</template>

<style lang="scss">
header {
  display: flex;
  height: fn.pxToRem(60);
  margin-left: fn.pxToRem(3);
  border-bottom-left-radius: fn.pxToRem(15);

  @include mx.prop('background-color', 'surface');
  @include mx.prop('box-shadow', 5px, 5px, 10px, 'shadow2');
  @include mx.prop('border-left', 1px, solid, 'secondary');
  @include mx.prop('border-top', 1px, solid, 'secondary');
}
</style>
