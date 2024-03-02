<template>
    <!-- Icon Container -->
    <div
        class="w-full flex flex-wrap justify-center md:w-[400px] relative"
        id="icons-container"
    >
        <!-- Upper Icons Container -->

        <div class="flex justify-between w-full md:w-[400px] z-20">
            <Icon
                icon="icon-paper"
                customColors="border-paper-gradient-1 shadow-[2px_7px_0px_0px_rgba(43,56,122)]"
            />
            <Icon
                icon="icon-scissors"
                customColors="border-scissors-gradient-1 shadow-[2px_7px_0px_0px_rgba(183,123,11)]"
            />
        </div>
        <div class="w-full flex justify-center mt-10 z-20">
            <Icon
                icon="icon-rock"
                customColors="border-rock-gradient-1 shadow-[2px_7px_0px_0px_rgba(167,53,74)]"
            />
        </div>

        <!-- Background triangle thing behind icons -->

        <img
            src="../../assets/images/bg-triangle.svg"
            alt="background triangle"
            class="w-full h-full absolute scale-75 z-10"
        />
    </div>
</template>

<script setup>
import Icon from "./Icon.vue";
</script>

<style lang="scss" scoped></style>
