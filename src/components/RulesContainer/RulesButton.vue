<template>
    <!-- Rules Button -->
    <div
        class="flex justify-center items-center absolute bottom-0 md:right-0 md:mr-5"
    >
        <button
            @click="handleClick"
            class="uppercase mb-6 border-2 border-header-outline rounded-lg px-10 py-2 hover:border-white transition-all"
        >
            <p class="tracking-widest">Rules</p>
        </button>
    </div>
</template>

<script setup>
import { rulesModal } from "../../store/store";

function handleClick() {
    rulesModal.value = true;
}
</script>

<style lang="scss" scoped></style>
