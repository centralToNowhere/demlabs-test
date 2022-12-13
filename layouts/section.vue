<template lang="pug">
  .content
    .content__main
      .content__main-header
        slot(name="content-header")
      .content__main-list-container
        slot(name="content-list")
    .content__controls
      slot(name="content-controls")
</template>

<style lang="scss">
@use '~style/functions' as fn;
@use '~style/mixins' as mx;
@use '~style/variables' as vars;

.content {
  display: flex;
  flex: 1;
  margin: fn.pxToRem(24) 0 fn.pxToRem(24) fn.pxToRem(24);

  &__main {
    display: flex;
    flex-direction: column;
    flex: 1;
    border-radius: fn.pxToRem(12);
    transition: background-color 0.5s linear 0s;

    @include mx.themify() using ($p) {
      background-color: fn.color('surface2', $p);
      box-shadow: inset 3px 3px 5px fn.color('shadow5', $p),
        1px 1px fn.color('shadow3', $p);
    }

    &-header {
      padding: fn.pxToRem(12) fn.pxToRem(16);
      line-height: fn.pxToRem(17.5);

      @include mx.font(14, 'bold');
      @include mx.themify() using ($p) {
        color: fn.color('primary', $p);
      }
    }

    &-title {
      line-height: fn.pxToRem(15);
      padding: fn.pxToRem(8) fn.pxToRem(16) fn.pxToRem(7);
      @include mx.font(12, 'medium');
      @include mx.themify() using ($p) {
        background-color: fn.color('surface9', $p);
        color: fn.color('primary', $p);
      }

      @include mx.themify('light') using ($p) {
        color: fn.color('surface', $p);
      }
    }

    &-item {
      line-height: fn.pxToRem(24);
      height: fn.pxToRem(50);
      display: flex;
      align-items: center;
      margin: 0 fn.pxToRem(16);
      cursor: pointer;
      @include mx.font(16, 'regular');
      @include mx.themify() using($p) {
        border-bottom: 1px solid fn.color('surface', $p);
        color: fn.color('primary', $p);
      }
    }

    &-list-container {
      display: flex;
      flex-direction: column;
    }
  }

  &__controls {
    display: flex;
    flex-direction: column;
    width: fn.pxToRem(398);
    padding: fn.pxToRem(12) fn.pxToRem(40) 0 fn.pxToRem(40);
  }
}
</style>
