<template>
    <div
        class="md:w-[190px] flex-col justify-center items-center px-14 mt-10 md:p-0"
        id="results-container-d"
    >
        <!-- Result Text -->

        <p class="text-5xl uppercase font-barlow-semi-condensed">
            {{ resultText }}
        </p>

        <!-- Back Button -->
        <BackButton />
    </div>
</template>

<script setup>
import BackButton from "./BackButton.vue";
import { computerPick, playerPick, score, winner } from "../../../store/store";
import { ref, watch } from "vue";

// Watch the icon picks and update the values when anything changes
watch([playerPick, computerPick], (value) => {
    determineWinner();
});

const resultText = ref("");

function determineWinner() {
    if (
        playerPick.value?.icon === "icon-rock" &&
        computerPick.value?.icon === "icon-rock"
    ) {
        tie();
    }
    if (
        playerPick.value?.icon === "icon-paper" &&
        computerPick.value?.icon === "icon-paper"
    ) {
        tie();
    }
    if (
        playerPick.value?.icon === "icon-scissors" &&
        computerPick.value?.icon === "icon-scissors"
    ) {
        tie();
    }

    if (
        playerPick.value?.icon === "icon-rock" &&
        computerPick.value?.icon === "icon-scissors"
    ) {
        win();
    }
    if (
        playerPick.value?.icon === "icon-paper" &&
        computerPick.value?.icon === "icon-rock"
    ) {
        win();
    }
    if (
        playerPick.value?.icon === "icon-scissors" &&
        computerPick.value?.icon === "icon-paper"
    ) {
        win();
    }

    if (
        playerPick.value?.icon === "icon-rock" &&
        computerPick.value?.icon === "icon-paper"
    ) {
        lose();
    }
    if (
        playerPick.value?.icon === "icon-paper" &&
        computerPick.value?.icon === "icon-scissors"
    ) {
        lose();
    }
    if (
        playerPick.value?.icon === "icon-scissors" &&
        computerPick.value?.icon === "icon-rock"
    ) {
        lose();
    }
}

function tie() {
    resultText.value = "You Tied";

    // Set the winner to no one
    winner.value = "";

    // Save new score to local storage
    Number(localStorage.setItem("score", score.value));
}

function win() {
    resultText.value = "You win";
    score.value = score.value + 1;

    // Set the winner to player
    winner.value = "player";

    // Save new score to local storage
    Number(localStorage.setItem("score", score.value));
}

function lose() {
    resultText.value = "You lose";

    // Set the winner to computer
    winner.value = "computer";

    score.value = score.value - 1;
    // Save new score to local storage
    Number(localStorage.setItem("score", score.value));
}
</script>

<style lang="scss" scoped></style>
