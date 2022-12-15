<script>

import { store } from '../store';

export default {
    name: "AppFilter",
    data() {
        return {
            store,
            options: [
                {
                    value: "",
                    disabled: true,
                    text: "Select category"
                },
                {
                    value: "",
                    disabled: false,
                    text: ""
                },
                {
                    value: "alive",
                    disabled: false,
                    text: "alive"
                },
                {
                    value: "dead",
                    disabled: false,
                    text: "dead"
                },
                {
                    value: "unknown",
                    disabled: false,
                    text: "unknown"
                }
            ]
        }
    }
}
</script>

<template>

    <div class="container">
        <select v-model="store.select" @click="$emit('filter')">
            <option :disabled="option.disabled" v-for="(option, index) in options" :value="option.value" :key="index">{{
                    option.text
            }}</option>
        </select>
    </div>

</template>

<style lang="scss">
@use '../styles/general.scss' as *;
</style>
