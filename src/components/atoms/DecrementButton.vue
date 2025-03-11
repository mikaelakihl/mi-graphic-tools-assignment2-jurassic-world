<script lang="ts" setup>
defineProps({
    buttonText: {type: String, required: true },
});
</script>
<template>
  <button>
    {{ buttonText }}
  </button>
</template>
<style lang="scss" scoped>
button {
  height: 2.8125rem;
  width: 2.8125rem;
  border: none;
  border-radius: 8px;
  margin: 0.2rem;
  background-color: #d9d9d9;
  @include h2;

  &:hover {
    background-color: $yellow;
  }

  &:active {
    background-color: $red;
  }
}

.active {
  background-color: $lightyellow;
}
</style>
