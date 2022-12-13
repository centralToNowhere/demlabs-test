<template lang="pug">
  -
    const searchIconPath = '/icons/search.svg'

  .search
    .search__icon
      NuxtImg(src=searchIconPath)
    input.search__input(type="search" placeholder="Search")

</template>

<script lang="ts">
import { defineComponent } from 'vue'
import ButtonComponent from '~/components/button/index.vue'

export default defineComponent({
  name: 'SearchComponent',
  components: {
    ButtonComponent,
  },
})
</script>

<style lang="scss">
@use '~style/functions' as fn;
@use '~style/mixins' as mx;
@use '~style/variables' as vars;

.search {
  display: flex;
  width: fn.pxToRem(224);

  @include mx.themify() using ($p) {
    border-bottom: 1px solid fn.color('surface7', $p);
  }

  &__input {
    background: transparent;
    outline: none;
    border: none;
    font-family: vars.$quicksand;
    margin-bottom: fn.pxToRem(6);
    line-height: fn.pxToRem(24);

    @include mx.font(16, 'regular');
    @include mx.themify() using ($p) {
      color: fn.color('text-secondary', $p);
    }
  }

  &__icon {
    $size: fn.pxToRem(20);
    width: $size;
    height: $size;
    margin: fn.pxToRem(2) fn.pxToRem(16) fn.pxToRem(8) 0;
  }
}
</style>
