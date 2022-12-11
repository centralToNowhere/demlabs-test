<template lang="pug">
  .logo
    NuxtImg(src="/Logo.svg")
</template>

<style lang="scss">
@use '~style/functions' as fn;

.logo {
  padding: fn.pxToRem(20) 0 fn.pxToRem(20) fn.pxToRem(24);
}
</style>
