<script>
export default {
    name: 'AppCard',
    props: {
        name: String,
        archetype: String,
        img: String,
    },
};
</script>

<template>
    <div class="card my-4" style="border: 1px solid black; height: 27rem;">
        <div class="card-header p-0" style="border: none;">
            <img :src="img" alt="" />
        </div>
        <div class="card-body text-center">
            <p>{{ name }}</p>
            <p>{{ archetype }}</p>
        </div>
    </div>
</template>

<style scoped lang="scss">
@use '../styles/appCard.scss';
</style>
