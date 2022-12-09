<template lang="pug">
  main.content
    .content__main
    .content__controls
</template>

<style lang="scss">
.content {
  display: flex;
  flex: 1;
  margin: fn.pxToRem(24) 0 fn.pxToRem(24) fn.pxToRem(24);

  &__main {
    display: flex;
    flex: 1;
    border-radius: fn.pxToRem(12);

    @include mx.prop('background-color', 'surface2');
  }

  &__controls {
    display: flex;
    width: fn.pxToRem(398);
    padding: 0 fn.pxToRem(40);
  }
}
</style>
