<script>
export default {
    name: 'AppNav',
}
</script>

<template>

<nav>
    <img src="https://vignette1.wikia.nocookie.net/yugiohenespanol/images/a/aa/Yugioh_anime_logo.jpg/revision/latest?cb=20130310042737&path-prefix=es" alt="logo Yu-Gi-Oh">
    <h1>
        Yu-Gi-Oh Api
    </h1>
</nav>

</template>

<style lang="scss">
 nav {
    display: flex;
    align-items: center;
    background-color: white;
    color: black;
    padding: 24px 36px;
    gap: 36px;

    img {
        height: 34px;
    }

    h1 {
        font-size: 40px;
        font-weight: 400;
    }
 }
</style>