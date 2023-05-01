<template>
    <div id="app">
        <CalculatorCod3r />
    </div>
</template>

<script>
import CalculatorCod3r from './main/CalculatorCod3r'

export default {
    components: { CalculatorCod3r }
}
</script>

<style>
    @font-face {
        font-family: "RobotoMono";
        src: url("./fonts/Roboto-Thin.ttf");
    }

    * {
        font-family: 'RobotoMono', monospace;
    }

    body {
        margin: 0;
    }

    #app {
        display: flex;
        flex-direction: column;
        height: 100vh;
        justify-content: center;
        align-items: center;
        text-align: center;

        color: #fff;
        background: rgb(238,174,202);
        background: radial-gradient(circle, rgba(238,174,202,1) 0%, rgba(148,187,233,1) 100%);
    }
</style>