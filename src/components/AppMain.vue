<script>

import SingleCharacter from './SingleCharacter.vue'

import { store } from '../store.js'

export default {
    name: "AppMain",
    components: {
        SingleCharacter,
    },
    data() {
        return {
            store,
        }
    }
}

</script>

<template>

    <section class="container">
        <div v-for="character in store.characterList" :key="character.id" class="card">
            <SingleCharacter :info="character" />
        </div>
    </section>

</template>

<style lang="scss" scoped>
@use '../styles/partials/variables' as *;

.container {
    display: flex;
    flex-wrap: wrap;
    max-width: 1024px;
    margin: 0 auto;
    background-color: #fff;
    padding: 20px;

    .card {
        width: calc(100% / 5 - 20px);
        margin: 10px;
        background-color: $color-primary;
        padding: 10px;
        text-align: center;
        color: #fff;
    }
}
</style>