<script setup>
import { defineProps } from "vue";
import { RouterLink } from "vue-router";

const props = defineProps(["quiz"]);
</script>

<template>
    <RouterLink class="card" :to="`/quiz/${props.quiz.id}`">
        <img :src="props.quiz.img" alt="preview">
        <div class="card-text">
            <h2>{{ props.quiz.name }}</h2>
            <p>{{ props.quiz.questions.length }} questions</p>
        </div>
    </RouterLink>
</template>

<style scoped>
.card {
    width: 310px;
    overflow: hidden;
    border-radius: 5px;
    box-shadow: 1px 1px 10px #00000019;
    margin-bottom: 35px;
    margin-right: 20px;
    cursor: pointer;
    color: var(--vt-c-text-light-1);
    text-decoration: none;
}

.card > img {
    width: 100%;
    height: 190px;
    margin: 0;
}

.card > .card-text {
    padding: 0 5px;
}

.card > .card-text > h2 {
    font-weight: 600;
}
</style>