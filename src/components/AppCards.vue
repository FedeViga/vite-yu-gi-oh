<script>
import { store } from '../store';

import CardItem from './CardItem.vue';

export default {
    name: 'AppCards',

    components: {
        CardItem,
    },

    data() {
        return {
            store,
        }
    }
}
</script>

<template>

    <section>

        <div class="content">

            <div class="cards-title">
                <h2>
                    Found {{ store.cards.length }} Cards
                </h2>
            </div>
            <div class="cards-list">
    
                <CardItem 
                    v-for="currentCard in store.cards"
                    :card="currentCard"
                ></CardItem>
                
            </div>

        </div>

    </section>
</template>

<style lang="scss">

section {

    .cards-title {
        background-color: black;
        color: white;
        padding: 30px 24px;
        font-size: 14px;
    }

    .cards-list {
        display: flex;
        flex-wrap: wrap;
        gap: 36px;
    }
}
</style>