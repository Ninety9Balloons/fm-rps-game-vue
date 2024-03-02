<template>
    <div
        class="p-7 min-h-screen w-full max-w-[400px] md:max-w-[800px] max-h-[700px] flex flex-col justify-center md:items-center"
    >
        <!-- Header -->
        <Header />

        <!-- Hero Icons Container -->
        <IconsContainer v-show="!playerPick" />

        <!-- Picked Icons -->
        <PickedIcons v-show="playerPick" />
    </div>
</template>

<script setup>
import IconsContainer from "./IconsContainer/IconsContainer.vue";
import Header from "./header/Header.vue";

import { playerPick, score } from "../store/store";
import PickedIcons from "./PickedIcons/PickedIcons.vue";

// Set the score to whatever value is saved in local storage
score.value = Number(localStorage.getItem("score"));
</script>

<style lang="scss" scoped></style>
