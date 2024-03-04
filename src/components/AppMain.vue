<script>
import AppCards from './AppCards.vue';

export default {
    name: 'AppMain',

    components: {
        AppCards,
    }
}
</script>

<template>

    <main>
        <div class="container">

            <AppCards></AppCards>
            
        </div>
    </main>


</template>

<style lang="scss">

@use '../styles/variables' as *; 

main {

    background-color: $primary;
    padding: 124px 10px;

    .container {
        max-width: 1680px;
        width: 100%;
        background-color: white;
        color: black;
        padding: 70px;
        margin: 0 auto;
    }
}
</style>