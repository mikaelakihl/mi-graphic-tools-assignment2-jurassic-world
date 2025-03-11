<template>
  <button>Book Now</button>
</template>

<style lang="scss" scoped>
button {
  width: 117px;
  height: 47px;
  background-color: $yellow;
  padding: 0.5rem;
  border: 0;
  border-radius: 8px;
  box-shadow: 0px 4px 4px 0px #00000040;
  @include h2;

  &:active {
    background-color: $lightyellow;
  }
}
</style>
