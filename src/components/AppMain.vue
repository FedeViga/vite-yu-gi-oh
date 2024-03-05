<script>
import { store } from '../store';
import AppCards from './AppCards.vue';
import AppLoading from './AppLoading.vue';

export default {
    name: 'AppMain',

    components: {
        AppCards,
        AppLoading
    },

    data() {
        return {
            store,
        }
    }
}
</script>

<template>

    <main>
        <div class="container">

            <AppCards v-if="store.loaded"></AppCards>

            <AppLoading v-else></AppLoading>
            
        </div>
    </main>


</template>

<style lang="scss">

@use '../styles/variables' as *; 

main {

    background-color: $primary;
    padding: 0px 10px 20px 10px;

    .container {
        max-width: 1680px;
        width: 100%;
        background-color: white;
        color: black;
        padding: 70px;
        margin: 0 auto;
        border-radius: 20px;
        box-shadow: $box-shadow-primary;
    }
}
</style>