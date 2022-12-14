<script>
export default {
    name: "SingleCharacter",
    props: ["info"]
}
</script>

<template>

    <img :src="info.image" :alt="info.name">

</template>

<style lang="scss" scoped>
@use '../styles/partials/variables' as *;
</style>