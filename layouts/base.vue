<template lang="pug">
  .base-layout
    .base-layout__row
      SidebarComponent
      .base-layout__col
        BaseHeader
        Nuxt
    BaseFooter
</template>

<style lang="scss">
@use '~style/mixins' as mx;
@use '~style/functions' as fn;

html,
body,
#__nuxt,
#__layout,
.base-layout {
  height: 100%;
}

.base-layout {
  display: flex;
  flex-direction: column;
  justify-content: stretch;
  transition: background-color 0.5s linear 0s;

  @include mx.themify() using ($p) {
    background-color: fn.color('surface', $p);
  }
}

.base-layout__row {
  display: flex;
  flex: 1;
}

.base-layout__col {
  display: flex;
  flex-direction: column;
  flex: 1;
}
</style>
