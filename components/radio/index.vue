<template lang="pug">
  label.radiobutton
    input(type="radio" :value="radioValue" :name="radioName")
    .radiobutton__marker-container
      .radiobutton__marker-dot
      svg(xmlns="http://www.w3.org/2000/svg" version="1.1" width="20" height="20" viewBox="0 0 20 20")
        defs
          linearGradient(id="radioGradient")
            stop(offset="0%")
            stop(offset="100%")
        circle(cx="10" cy="10" r="6.5" stroke-width="7")
    span.radiobutton__title {{ radioTitle }}
</template>

<script>
import Vue from 'vue'

export default Vue.extend({
  name: 'RadioButton',
  props: {
    radioTitle: {
      type: String,
      default: '',
    },
    radioName: {
      type: String,
      default: '',
    },
    radioValue: {
      type: String,
      default: '',
    },
  },
})
</script>
<style lang="scss">
@use '~style/mixins' as mx;
@use '~style/functions' as fn;
@use '~style/variables' as vars;

.radiobutton {
  $self: &;
  display: flex;
  position: relative;
  cursor: pointer;

  &__marker-dot {
    $size: fn.pxToRem(6);
    width: $size;
    height: $size;
    position: absolute;
    border-radius: 50px;

    @include mx.themify() using ($p) {
      background-color: fn.color('surface4', $p);
    }
  }

  &__marker-container {
    $size: fn.pxToRem(20);
    width: $size;
    height: $size;
    display: flex;
    justify-content: center;
    align-items: center;
    border-radius: fn.pxToRem(50);
    overflow: hidden;

    @include mx.themify() using ($p) {
      box-shadow: inset 1px 1px 3px fn.color('shadow6', $p),
        2px 2px 5px fn.color('shadow5', $p);
    }
  }

  & circle {
    fill: transparent;
    @include mx.themify() using ($p) {
      stroke: fn.color('surface5', $p);
    }
  }

  & svg stop:nth-child(1) {
    @include mx.themify() using ($p) {
      stop-color: fn.color('accent', $p);
    }
  }

  & svg stop:nth-child(2) {
    @include mx.themify() using ($p) {
      stop-color: fn.color('accent2', $p);
    }
  }

  &__title {
    margin-left: fn.pxToRem(16);
    line-height: fn.pxToRem(20);
    font-family: vars.$quicksand;

    @include mx.font(16, 'regular');
    @include mx.themify() using ($p) {
      color: fn.color('primary', $p);
    }
  }

  input[type='radio'] {
    display: none;
  }

  input[type='radio']:checked {
    & ~ #{$self}__marker-container {
      @include mx.themify() using ($p) {
        box-shadow: inset 1px 1px 2px fn.color('shadow5', $p),
          2px 2px 5px fn.color('shadow7', $p);
      }

      #{$self}__marker-dot {
        background-color: transparent;
      }

      circle {
        stroke: url(#radioGradient);
      }
    }
  }
}
</style>
