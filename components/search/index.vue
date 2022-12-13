<template lang="pug">
  -
    const searchIconPath = '/icons/search.svg'

  .search
    .search__icon
      svg(xmlns="http://www.w3.org/2000/svg" width="20" height="20" viewBox="0 0 20 20" fill="none")
        path(fill-rule="evenodd" clip-rule="evenodd" d="M4.39253 4.39252C2.58599 6.19905 2.58599 9.12803 4.39253 10.9346C6.19906 12.7411 9.12804 12.7411 10.9346 10.9346C12.7411 9.12803 12.7411 6.19906 10.9346 4.39252C9.12804 2.58598 6.19906 2.58598 4.39253 4.39252ZM3.83178 3.83177C5.94801 1.71554 9.3791 1.71554 11.4953 3.83177C13.5172 5.85368 13.6074 9.07587 11.7657 11.2048L16.1682 15.6075C16.3231 15.7623 16.3231 16.0134 16.1682 16.1682C16.0134 16.3231 15.7623 16.3231 15.6075 16.1682L11.205 11.7655C9.07608 13.6074 5.85376 13.5173 3.83178 11.4953C1.71555 9.37909 1.71555 5.948 3.83178 3.83177Z" fill="white")

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

    & path {
      @include mx.themify() using ($p) {
        fill: fn.color('primary', $p);
      }
    }
  }
}
</style>
