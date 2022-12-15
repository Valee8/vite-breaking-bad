<script>

import SingleCharacter from './SingleCharacter.vue'
import NumberOfCharacters from './NumberOfCharacters.vue'


import { store } from '../store.js'

export default {
    name: "AppMain",
    components: {
        SingleCharacter,
        NumberOfCharacters
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
        <div class="numbers-characters">
            <NumberOfCharacters v-if="store.select != ''" />
        </div>

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
    background-color: #fff;

    .card {
        width: calc(20% - 20px);
        margin: 10px;
        background-color: $color-primary;
        padding: 10px;
        text-align: center;
        color: #fff;
    }

    .numbers-characters {
        width: 100%;
    }

}
</style>