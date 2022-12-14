<script>
export default {
    name: "SingleCharacter",
    props: ["info"]
}
</script>

<template>

    <img :src="info.image" :alt="info.name">
    <h3 class="name">
        {{ info.name }}
    </h3>

    <div class="status">
        {{ info.status }}
    </div>

    <div class="species">
        {{ info.species }}
    </div>

</template>

<style lang="scss" scoped>
@use '../styles/partials/variables' as *;

.name {
    text-transform: uppercase;
    font-size: 0.8rem;
}

div {
    font-size: 0.7rem;
}
</style>