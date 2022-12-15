<script>
import { store } from '../store';

export default {
    name: "NumberOfCharacters",
    data() {
        return {
            store,
        }
    }
}

</script>


<template>

    <h1>
        {{ store.characterList.length }}
    </h1>

</template>


<style lang="scss">
@use '../styles/general.scss' as *;
</style>