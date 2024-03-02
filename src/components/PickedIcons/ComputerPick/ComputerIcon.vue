<template>
    <div>
        <!-- Only show when computerPick is empty -->
        <div
            v-show="!computerPick"
            className="bg-dark-text rounded-full opacity-25 w-[120px] h-[120px] md:w-[150px] md:h-[150px]"
        ></div>
        <!-- Only show when computerPick has picked something -->
        <img
            v-show="computerPick"
            :src="getImageUrl()"
            class="bg-white rounded-full p-7 flex justify-center items-center border-[15px] w-[120px] h-[120px] md:w-[150px] md:h-[150px] hover:-translate-y-2 transition-all cursor-pointer"
            :class="setCustomColors()"
        />
    </div>
</template>

<script setup>
import { computerPick } from "../../../store/store";

function getImageUrl() {
    return new URL(
        `../../../assets/images/${computerPick.value?.icon}.svg`,
        import.meta.url
    );
}

function setCustomColors() {
    return computerPick.value?.customColors;
}
</script>

<style lang="scss" scoped></style>
