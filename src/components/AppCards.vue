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
                    Cards Found: {{ store.cardsFoundNumber }}
                </h2>

                <h2>
                    Cards Shown: {{ store.cards.length }}
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

@use '../styles/variables' as *; 

section {

    .cards-title {
        display: flex;
        justify-content: space-between;
        background-color: black;
        color: white;
        padding: 30px 24px;
        font-size: 14px;
        border-radius: 20px;
        margin-bottom: 20px;
        box-shadow: $box-shadow-primary;
    }

    .cards-list {
        display: flex;
        flex-wrap: wrap;
        gap: 36px;
    }
}
</style>