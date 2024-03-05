<script>

export default {
    name: 'AppLoading',
}

</script>

<template>
    <div class="loading">
        <div class="spinner">
            <div></div><div></div><div></div><div></div>

        </div>
        <div>
            LOADING...
        </div>
    </div>
</template>

<style lang="scss">

.loading {
    display: flex;
    justify-content: center;
    font-size: 3em;
    text-align: center;
    gap: 0;

    .spinner {
        display: inline-block;
        position: relative;
        width: 80px;
        height: 80px;
        transform: scale(.7);

        div {
            box-sizing: border-box;
            display: block;
            position: absolute;
            width: 64px;
            height: 64px;
            margin: 8px;
            border: 8px solid black;
            border-radius: 50%;
            animation: spinning 1.2s cubic-bezier(0.5, 0, 0.5, 1) infinite;
            border-color: black transparent transparent transparent;
        }
    
        div:nth-child(1) {
            animation-delay: -0.45s;
        }
    
        div:nth-child(2) {
            animation-delay: -0.3s;
        }
        div:nth-child(3) {
            animation-delay: -0.15s;
        }
    }
    
}

@keyframes spinning {
    0% {
        transform: rotate(0deg);
    }
    100% {
        transform: rotate(360deg);
    }
}
</style>