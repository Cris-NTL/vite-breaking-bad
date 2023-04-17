<script>
export default {
    name: "AppCard",
    props: {
        name: String,
        archetype: String,
        img: String,
    }
}
</script>

<template>
    <div class="card">
        <div class="card-header">
            <img :src="img" alt="">
        </div>
        <div class="card-body">
            <p>{{ name }}</p>
            <p>{{ archetype }}</p>
        </div>
    </div>
</template>
  
<style scoped lang="scss">
@use "../styles/appCard.scss";
</style>