<template lang="pug">
  button.button(:disabled="buttonDisabled" v-bind:class="classObject") {{ buttonTitle }}
</template>

<script>
import Vue from 'vue'

export default Vue.extend({
  name: 'DefaultButton',
  props: {
    buttonTitle: {
      type: String,
      default: '',
    },
    buttonSize: {
      type: String,
      default: 'small',
    },
    buttonDisabled: {
      type: Boolean,
      default: false,
    },
  },
  computed: {
    classObject: function () {
      return {
        button_large: this.buttonSize === 'large',
      }
    },
  },
})
</script>

<style lang="scss">
@use '~style/mixins' as mx;
@use '~style/functions' as fn;
@use '~style/variables' as vars;

.button {
  display: flex;
  align-items: center;
  justify-content: center;
  height: fn.pxToRem(24);
  line-height: fn.pxToRem(18);
  border-radius: fn.pxToRem(24);
  width: 100%;
  font-family: vars.$quicksand;
  @include mx.font(12, 'medium');

  @include mx.themify() using ($p) {
    color: fn.color('primary', $p);
    background: linear-gradient(
      230.15deg,
      fn.color('light-accent', $p) 0%,
      fn.color('light-accent2', $p) 92.48%
    );
    box-shadow: 2px 2px 7px fn.color('shadow8', $p),
      inset 1px 1px 4px fn.color('shadow9', $p);
  }

  &_large {
    height: fn.pxToRem(36);
    border-radius: fn.pxToRem(30);
    line-height: fn.pxToRem(24);
    @include mx.font(14, 'medium');
  }

  &:hover {
    @include mx.themify() using ($p) {
      background: linear-gradient(
        230.15deg,
        fn.color('light-accent', $p) 0%,
        fn.color('light-accent3', $p) 92.48%
      );
    }
  }

  &:active {
    @include mx.themify() using ($p) {
      background: linear-gradient(
        90deg,
        fn.color('accent', $p) 0%,
        fn.color('accent2', $p) 92.48%
      );
      box-shadow: 2px 2px 5px fn.color('shadow7', $p),
        inset 1px 1px 2px fn.color('shadow5', $p);
    }
  }

  &:disabled {
    cursor: not-allowed;
    @include mx.themify() using ($p) {
      background: fn.color('surface3', $p);
      box-shadow: 2px 2px 7px fn.color('shadow8', $p),
        inset 1px 1px 4px fn.color('shadow10', $p);
    }
  }
}
</style>
