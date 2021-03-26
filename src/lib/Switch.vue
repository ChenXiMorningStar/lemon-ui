<template>
  <button class="gulu-switch" @click="toggle" :class="{'gulu-checked':value}" :disabled="disabled">
    <span></span>
  </button>
</template>
<script lang="ts">
export default {
  props: {
    value: Boolean,
    disabled: {
      type: Boolean,
      default: false
    }
  },
  setup(props, context) {
    const toggle = () => {
      context.emit("update:value", !props.value);
    };
    return { toggle };
  }
};
</script>

<style lang="scss">
$h: 22px;
$h2: $h - 4px;
.gulu-switch {
  height: $h;
  width: $h * 2;
  border: none;
  background: #bfbfbf;
  border-radius: $h/2;
  position: relative;
  > span {
    position: absolute;
    top: 2px;
    left: 2px;
    height: $h2;
    width: $h2;
    background: white; border-radius: $h2 / 2;
    transition: all 250ms;
  }
  &[disabled] {
    cursor: not-allowed;
  }
  &.gulu-checked { background: #1890ff;
    > span { left: calc(100% - #{$h2} - 2px); }
  }
  &:focus { outline: none; }
  // 点击的时候让小圆圈变胖
  &:active {
    > span { width: $h2 + 4px; }
  }
  &.gulu-checked:active {
    > span { width: $h2 + 4px; margin-left: -4px; }
  }
}
</style>