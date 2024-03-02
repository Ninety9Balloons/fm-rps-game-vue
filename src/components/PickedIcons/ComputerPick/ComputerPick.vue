<template>
    <div class="flex flex-col items-center">
        <!-- Text Desktop -->
        <p class="uppercase mb-8 tracking-widest hidden md:block">
            The House picked
        </p>

        <!-- Placeholder -->

        <!-- Icon -->
        <ComputerIcon
            :class="
                winner === 'computer'
                    ? 'drop-shadow-[0_0px_35px_rgba(255,255,255,.5)]'
                    : ''
            "
        />

        <!-- Text Mobile -->
        <p class="uppercase mt-8 tracking-widest md:hidden">The House picked</p>
    </div>
</template>

<script setup>
import { winner } from "../../../store/store";
import ComputerIcon from "./ComputerIcon.vue";
</script>

<style lang="scss" scoped></style>
