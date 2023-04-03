<script setup>
import q from "../data/quizes.json";
import { ref, watch } from "vue";

import QuizCard from "@/components/QuizCard.vue";

const quizes = ref(q);
const search = ref("");

watch(search, () => {
    quizes.value = q.filter(quiz => quiz.name.toLowerCase().includes(search.value.toLowerCase()));
});
</script>

<template>
    <div class="wrapper">
        <header>
            <h1>Quizes</h1>
            <input v-model.trim="search" type="text" placeholder="Search...">
        </header>
        <div class="cards-wrapper">
            <QuizCard v-for="quiz in quizes" :key="quiz.id" :quiz="quiz" />
        </div>
    </div>
</template>

<style scoped>
.wrapper {
    max-width: 1000px;
    margin: 0 auto;
}

header {
    display: flex;
    align-items: center;
    margin-bottom: 10px;
    margin-top: 30px;
}

header > h1 {
    font-weight: 600;
    margin-right: 30px;
}

header > input {
    border: none;
    background: #80808019;
    padding: 10px;
    border-radius: 5px;
}

.cards-wrapper {
    display: flex;
    flex-wrap: wrap;
    margin-top: 40px;
}
</style>
