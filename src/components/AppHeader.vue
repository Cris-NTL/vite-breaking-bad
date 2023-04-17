<script>
export default {
    name: "AppHeader",
    props: {
        title: String
    }
}
</script>

<template>
    <header>
        <h2 class="p-3">{{ title }}</h2>
    </header>
</template>

<style scoped lang="scss">
@use "../styles/appHeader.scss";
</style>