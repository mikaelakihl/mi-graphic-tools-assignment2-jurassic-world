<script setup lang="ts">
    defineProps( {
        buttonText: { type: String, required: true },
    });
</script>
<template>
    <button> {{ buttonText }}</button>
</template>
<style lang="scss" scoped>
button {
    background-color: $lightgreen;
    color: $white;
    width: 11.5625rem;
    height: 2.9375rem;
    border-radius: 8px;
    border: none;
    box-shadow: 0px 4px 4px 0px #00000040;
    margin: 0.5rem;
    @include h2;

    &:hover {
        background-color: #A3A3A3;
    }

    &:active {
        background-color: $green;
    }
}
</style>
