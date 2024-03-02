<template>
    <!-- Rules Modal -->
    <div
        v-show="rulesModal"
        class="flex flex-col justify-between items-center px-7 py-20 bg-white w-full h-full min-w-screen min-h-screen absolute z-30"
    >
        <p class="text-3xl uppercase font-bold text-dark-text">Rules</p>
        <img src="../../assets/images/image-rules.svg" alt="Rules image" />
        <button
            class="p-5 hover:brightness-[.25] transition-all"
            @click="handleClick()"
        >
            <img src="../../assets/images/icon-close.svg" alt="Close icon" />
        </button>
    </div>
</template>

<script setup>
import { rulesModal } from "../../store/store";

function handleClick() {
    rulesModal.value = false;
}
</script>

<style lang="scss" scoped></style>
