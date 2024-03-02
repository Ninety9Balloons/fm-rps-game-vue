<template>
    <div>
        <img
            :src="getImageUrl()"
            :alt="props.icon"
            class="bg-white rounded-full p-7 flex justify-center items-center border-[15px] w-[120px] h-[120px] md:w-[150px] md:h-[150px] hover:-translate-y-2 transition-all cursor-pointer"
            :class="props.customColors"
            @click="handleClick()"
        />
    </div>
</template>

<script setup>
import { playerPick, computerPick } from "../../store/store";

const paperIcon = {
    icon: "icon-paper",
    customColors:
        "border-paper-gradient-1 shadow-[2px_7px_0px_0px_rgba(43,56,122)]",
};

const scissorsIcon = {
    icon: "icon-scissors",
    customColors:
        "border-scissors-gradient-1 shadow-[2px_7px_0px_0px_rgba(183,123,11)]",
};

const rockIcon = {
    icon: "icon-rock",
    customColors:
        "border-rock-gradient-1 shadow-[2px_7px_0px_0px_rgba(167,53,74)]",
};

const props = defineProps(["icon", "customColors"]);

// Set the img src to the location of images
function getImageUrl() {
    return new URL(`../../assets/images/${props.icon}.svg`, import.meta.url);
}

function handleClick() {
    playerPick.value = { icon: props.icon, colors: props.customColors };

    const icons = [paperIcon, scissorsIcon, rockIcon];

    // Select a random icon for the computer, give it a 1 second delay
    setTimeout(() => {
        const randomIcon = Math.floor(Math.random() * icons.length);

        computerPick.value = icons[randomIcon];
    }, 1000);
}
</script>

<style lang="scss" scoped></style>
