<template>
    <div class="flex w-full justify-around md:py-44 flex-wrap">
        <div class="order-first">
            <!-- Player Pick -->
            <PlayerPick />
        </div>

        <!-- Moves the results under the icons for small screens, and between icons for larger screens -->
        <!-- Only shows the results when there's something in the computerPick store -->
        <div v-show="computerPick" class="order-last md:order-[0]">
            <!-- Results  -->
            <Results />
        </div>

        <!-- Computer Pick -->
        <ComputerPick />
    </div>
</template>

<script setup>
import ComputerPick from "./ComputerPick/ComputerPick.vue";
import PlayerPick from "./PlayerPick.vue";
import Results from "./Results/Results.vue";

import { computerPick } from "../../store/store";


</script>

<style lang="scss" scoped></style>
