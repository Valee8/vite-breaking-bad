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

    <section class="container">
        <h2>
            Found {{ store.characterList.length }} characters
        </h2>
    </section>

</template>


<style lang="scss">
@use '../styles/general.scss' as *;
</style>