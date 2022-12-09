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
  @include mx.prop('background-color', 'surface');
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
