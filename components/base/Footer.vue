<template lang="pug">
  -
    const nets = [
      {
        name: "Cellnet",
        status: "active"
      },
      {
        name: "Mainnet",
        status: "active"
      },
      {
        name: "Somenet",
        status: "active",
      },
      {
        name: "Testnet",
        status: "active"
      }
    ]

  mixin statusBar(items=[])
    each item in items
      .footer-bar__item
        if item.name
          span= item.name
        -
          const indicatorClass = `footer-bar__item-indicator ${ item.status === 'active'
           ? 'footer-bar__item-indicator_active' : ''}`

        div(class=indicatorClass)

  footer.footer-bar
    +statusBar(nets)
</template>

<style lang="scss">
@use '~style/functions' as fn;
@use '~style/mixins' as mx;

.footer-bar {
  display: flex;
  height: fn.pxToRem(42);
  margin-top: fn.pxToRem(5);
  padding: 0 fn.pxToRem(50);
  transition: background-color 0.5s linear 0s;

  @include mx.themify() using ($p) {
    background-color: fn.color('surface', $p);
    box-shadow: 5px -5px 10px fn.color('shadow2', $p),
      inset 1px 1px fn.color('shadow4', $p);
    border-left: 1px solid fn.color('secondary', $p);
    border-top: 1px solid fn.color('secondary', $p);
  }

  &__item {
    display: flex;
    align-items: center;
    justify-content: center;
    flex-grow: 1;
    line-height: fn.pxToRem(15);

    @include mx.font(12, 'medium');
    @include mx.themify() using ($p) {
      color: fn.color('primary', $p);
    }
  }

  &__item-indicator {
    width: fn.pxToRem(8);
    height: fn.pxToRem(8);
    border-radius: 50%;
    margin-left: fn.pxToRem(8);

    &_active {
      @include mx.themify() using ($p) {
        background: radial-gradient(
          fn.color('indicator-active', $p),
          fn.color('indicator-active2', $p)
        );
      }
    }
  }
}
</style>
