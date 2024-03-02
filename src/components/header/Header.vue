<template>
    <div
        class="border-2 border-header-outline md:max-w-[600px] md:w-[600px] flex justify-between rounded-lg p-2 md:p-4 uppercase items-center absolute top-0 left-0 right-0 self-center m-5 md:mx-auto"
    >
        <!-- Logo -->

        <img
            src="../../assets/images/logo.svg"
            class="w-24 md:w-36 ml-2"
            alt="Logo"
        />

        <!-- Score -->

        <div
            class="bg-white rounded-lg flex flex-col items-center px-5 md:px-8 py-2"
        >
            <p class="text-score-text tracking-widest text-sm md:text-md">
                Score
            </p>
            <p class="text-header-outline text-4xl md:text-6xl font-bold">
                {{ score }}
            </p>
        </div>
    </div>
</template>

<script setup>
import { score } from "../../store/store";
</script>

<style lang="scss" scoped></style>
