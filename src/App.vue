<template>
    <div
        class="flex flex-col justify-between items-center min-h-screen h-full w-full min-w-screen bg-gradient-to-b from-radial-gradient-1 to-radial-gradient-2 text-white relative"
    >
        <Rules />
        <MainContainer />
        <RulesButton />
    </div>
</template>

<script setup>
import MainContainer from "./components/MainContainer.vue";
import Rules from "./components/RulesContainer/Rules.vue";
import RulesButton from "./components/RulesContainer/RulesButton.vue";
</script>

<style scoped></style>
