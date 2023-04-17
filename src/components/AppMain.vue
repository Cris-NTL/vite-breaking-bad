<script>
import AppCard from './AppCard.vue';
import { store } from '../store';

export default {
    name: "AppMain",
    components: { AppCard },

    data() {
        return {
            store
        }
    }
}
</script>

<template>
    <main class="p-3">
        <div class="row row-cols-5">
            <div class="col" v-for="card in store.cards" :key="card.id">
                <AppCard :name="card.name" :archetype="card.archetype" :img="card.card_images[0].image_url" />
            </div>
        </div>
    </main>
</template>

<style scoped lang="scss">
@use "../styles/appMain.scss";
</style>