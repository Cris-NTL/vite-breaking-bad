<script>
import AppCard from './AppCard.vue';

export default {
    name: "AppMain",
    components: { AppCard },
    props: {
        cards: {
            type: Array,
            required: true,
        },
    },
}
</script>

<template>
    <main class="p-3">
        <div class="row row-cols-5">
            <div class="col" v-for="card in cards" :key="card.name">
                <AppCard :name="card.name" :archetype="card.archetype" :img="card.card_images[0].image_url" />
            </div>
        </div>
    </main>
</template>

<style scoped lang="scss">
@use "../styles/appMain.scss";
</style>