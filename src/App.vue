<script>
import axios from 'axios';
import AppNav from './components/AppNav.vue';

export default {

  data() {
    return {
      cards: [],
    }
  },

  created() {

    axios.get('https://db.ygoprodeck.com/api/v7/cardinfo.php?num=20&offset=0').then(result => {
      console.log(result.data.data)
      this.cards = result.data.data;
    })
  },

  components: {
    AppNav,
  },
}
</script>

<template>

  <AppNav></AppNav>

</template>

<style lang="scss">

</style>