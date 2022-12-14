<script>
export default {
    name: "AppHeader",
    data() {
        return {
            title: 'Rick and Morty Api'
        }
    }
}

</script>

<template>

    <header>
        <h1>
            {{ title }}
        </h1>
    </header>

</template>

<style lang="scss" scoped>
header {
    padding: 10px;

    h1 {
        color: #F8F9FA;
        text-align: left;
    }
}
</style>