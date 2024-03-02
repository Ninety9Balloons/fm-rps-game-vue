<template>
    <button
        class="uppercase bg-white text-dark-text rounded-lg w-full py-3 mt-5 tracking-widest hover:bg-header-outline hover:text-white transition-all"
        @click="handleClick"
    >
        Play Again
    </button>
</template>

<script setup>
import { computerPick, playerPick, winner } from "../../../store/store";

function handleClick() {
    computerPick.value = "";
    playerPick.value = "";
    winner.value = "";
}
</script>

<style lang="scss" scoped></style>
