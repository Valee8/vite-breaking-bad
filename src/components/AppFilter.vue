<script>

import { store } from '../store';

export default {
    name: "AppFilter",
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

    <select v-model="store.select" @click="$emit('filter')">
        <option v-for="(option, index) in options" :value="option.value" :key="index">{{ option.value }}</option>
    </select>

</template>

<style lang="scss">
@use '../styles/general.scss' as *;
</style>
