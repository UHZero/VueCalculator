<template>
    <div class="calculator">
        <DisplayCalc />
        <ButtonCalc label="AC" triple />
        <ButtonCalc label="" />
        <ButtonCalc label="" />
        <ButtonCalc label="" />
        <ButtonCalc label="" />
        <ButtonCalc label="" />
    </div>
</template>

<script>
import DisplayCalc from '../components/DisplayCalc';
import ButtonCalc from '../components/ButtonCalc';

export default {
    components: { ButtonCalc, DisplayCalc }
}
</script>

<style>
    .calculator {
        height: 320px;
        width: 235px;
        border-radius: 5px;
        overflow: hidden;

        display: grid;
        grid-template-columns: repeat(4, 25%);
        grid-template-rows: 1fr 48px 48px 48px 48px 48px;
        
    }
</style>