<template lang="pug">
  main.content
    .content__main
      .content__main-header
      .content__main-list
    .content__controls
</template>

<style lang="scss">
@use '~style/functions' as fn;
@use '~style/mixins' as mx;

.content {
  display: flex;
  flex: 1;
  margin: fn.pxToRem(24) 0 fn.pxToRem(24) fn.pxToRem(24);

  &__main {
    display: flex;
    flex: 1;
    border-radius: fn.pxToRem(12);

    @include mx.themify() using ($p) {
      background-color: fn.color('surface2', $p);
      box-shadow: inset 3px 3px 5px fn.color('shadow5', $p),
        1px 1px fn.color('shadow3', $p);
    }
  }

  &__controls {
    display: flex;
    width: fn.pxToRem(398);
    padding: 0 fn.pxToRem(40);
  }
}
</style>
