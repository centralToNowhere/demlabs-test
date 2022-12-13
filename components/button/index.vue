<template lang="pug">
  button.button(:disabled="buttonDisabled" v-bind:class="classObject") {{ buttonTitle }}
    if buttonType
      slot(name="button-icon")
</template>

<script lang="ts">
import { defineComponent, PropType } from 'vue'

interface ButtonProps {
  buttonTitle?: string
  buttonSize?: 'small' | 'large'
  buttonDisabled?: boolean
  buttonType?: 'default' | 'icon'
}

type ButtonClasses = {
  [key: string]: boolean
}

export default defineComponent({
  name: 'ButtonComponent',
  props: {
    buttonTitle: {
      type: String as PropType<ButtonProps['buttonTitle']>,
      default: '',
    },
    buttonSize: {
      type: String as PropType<ButtonProps['buttonSize']>,
      default: 'small',
    },
    buttonDisabled: {
      type: Boolean as PropType<ButtonProps['buttonDisabled']>,
      default: false,
    },
    buttonType: {
      type: String as PropType<ButtonProps['buttonType']>,
      default: 'default',
    },
  },
  computed: {
    classObject: function (): ButtonClasses {
      return {
        button_large: this.buttonSize === 'large',
        button_icon: this.buttonType === 'icon',
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

  @include mx.themify('light') using ($p) {
    color: fn.color('surface', $p);
  }

  &_large {
    padding: fn.pxToRem(6) 0;
    border-radius: fn.pxToRem(30);
    line-height: fn.pxToRem(24);
    @include mx.font(14, 'medium');
  }

  &_icon {
    background: transparent;
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
