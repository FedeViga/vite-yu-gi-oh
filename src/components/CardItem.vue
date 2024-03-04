<script>

export default {
    name: 'CardItem',

    props: {
        card: Object,
    }
}
</script>

<template>
    <div class="card">
        
        <img :src="card.card_images[0].image_url" alt="">

        <h3>
            {{card.name}}
        </h3>
        <h3 v-if="card.archetype">
            {{ card.archetype }}
        </h3>
        <h3 v-else>
            No Archetype
        </h3>
        
    </div>
</template>

<style lang="scss">

@use '../styles/variables' as *; 

.card {
    width: calc(100% / 5 - 36px / 5 * 4);
    background-color: $primary;
    text-align: center;

    img {
        display: block;
        width: 100%;
        margin-bottom: 30px;
    }

    h3:first-of-type {
        color: white;
        text-transform: uppercase;
        margin-bottom: 30px;
    }

    h3:last-child {
        margin-bottom: 30px;
    }
}
</style>