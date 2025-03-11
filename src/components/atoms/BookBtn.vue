<template>
  <button>Book Now</button>
</template>

<style lang="scss" scoped>
button {
  width: rem(117);
  height: rem(47);
  background-color: $yellow;
  padding: 0.5rem;
  border: 0;
  border-radius: rem(8);
  box-shadow: 0px 4px 4px 0px #00000040;
  @include h2;

  &:active {
    background-color: $lightyellow;
  }
}
</style>
