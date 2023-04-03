<script setup>
import { useRoute } from "vue-router";
import q from "../data/quizes.json";
import { ref } from "vue";

const route = useRoute()
const quizes = ref(q);

const getQuiz = quizes.value.find(quiz => quiz.id === route.params.id);
</script>

<template>
    <h1>Quiz</h1>
    <p>{{ getQuiz.name }}</p>
</template>