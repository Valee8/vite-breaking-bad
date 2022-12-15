<script>

import NumberOfCharacters from './NumberOfCharacters.vue'


import { store } from '../store';

export default {
    name: "AppFilter",
    components: {
        NumberOfCharacters
    },
    data() {
        return {
            store,
            options: [
                {
                    value: ""
                },
                {
                    value: "alive"
                },
                {
                    value: "dead"
                },
                {
                    value: "unknown"
                }
            ]
        }
    }
}
</script>

<template>

    <div class="container">
        <NumberOfCharacters />

        <select v-model="store.select" @click="$emit('filter')">
            <option disabled value="">Scegli</option>
            <option v-for="(option, index) in options" :value="option.value" :key="index">{{ option.value }}</option>
        </select>
    </div>

</template>

<style lang="scss">
@use '../styles/general.scss' as *;
</style>
