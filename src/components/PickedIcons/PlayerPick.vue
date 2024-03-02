<template>
    <div className="flex flex-col items-center">
        <!-- Text Desktop -->
        <p className="uppercase mb-8 tracking-widest hidden md:block">
            You picked
        </p>

        <!-- Icon -->
        <div>
            <img
                :src="getImageUrl()"
                class="bg-white rounded-full p-7 flex justify-center items-center border-[15px] w-[120px] h-[120px] md:w-[150px] md:h-[150px] hover:-translate-y-2 transition-all cursor-pointer"
                :class="[
                    setCustomColors(),
                    winner === 'player'
                        ? 'drop-shadow-[0_0px_35px_rgba(255,255,255,.5)]'
                        : '',
                ]"
            />
        </div>
        <!-- Text Mobile -->
        <p className="uppercase mt-8 tracking-widest md:hidden">You picked</p>
    </div>
</template>

<script setup>
import { playerPick, winner } from "../../store/store";

function getImageUrl() {
    return new URL(
        `../../assets/images/${playerPick.value?.icon}.svg`,
        import.meta.url
    );
}

function setCustomColors() {
    return playerPick?.value?.colors;
}
</script>

<style lang="scss" scoped></style>
