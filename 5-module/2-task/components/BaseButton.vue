<template>
  <component
    :is="tag"
    class="button"
    v-on="$listeners"
    :class="{ button_block: block }"
  >
    <slot />
  </component>
</template>

<script>
export default {
  name: 'BaseButton',
  props: {
    block: Boolean,
    tag: {
      type: String,
      default: 'button',
      validator: (tag) => {
        return ['button', 'a', 'router-link'].includes(tag);
      },
    },
  },
};
</script>

<style scoped>
.button {
  display: inline-block;
  padding: 10px 24px;
  font-weight: 700;
  font-size: 20px;
  line-height: 28px;
  color: initial;
  text-align: center;
  border: 4px solid transparent;
  transition: 0.2s all;
  outline: none;
  box-shadow: none;
  background-color: transparent;
  cursor: pointer;
  text-decoration: none;
}

.button.button_block {
  display: block;
  width: 100%;
}
</style>
