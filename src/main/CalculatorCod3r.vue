<template>
    <div class="calculator">
        <DisplayCalc :value="displayValue" />
        <ButtonCalc label="AC" triple @onClick="clearMemory" />
        <ButtonCalc label="/" operation @onClick="setOperation" />
        <ButtonCalc label="7" @onClick="addDigit" />
        <ButtonCalc label="8" @onClick="addDigit" />
        <ButtonCalc label="9" @onClick="addDigit" />
        <ButtonCalc label="*" operation @onClick="setOperation" />
        <ButtonCalc label="4" @onClick="addDigit" />
        <ButtonCalc label="5" @onClick="addDigit" />
        <ButtonCalc label="6" @onClick="addDigit" />
        <ButtonCalc label="-" operation @onClick="setOperation" />
        <ButtonCalc label="1" @onClick="addDigit" />
        <ButtonCalc label="2" @onClick="addDigit" />
        <ButtonCalc label="3" @onClick="addDigit" />
        <ButtonCalc label="+" operation @onClick="setOperation" />
        <ButtonCalc label="0" double @onClick="addDigit" />
        <ButtonCalc label="." @onClick="addDigit" />
        <ButtonCalc label="=" operation @onClick="setOperation" />
    </div>
</template>

<script>
import DisplayCalc from '../components/DisplayCalc';
import ButtonCalc from '../components/ButtonCalc';

export default {
    data() {
        return {
            displayValue: "0",
            clearDisplay: false,
            operation: null,
            values: [0, 0],
            current: 0
        }
    },
    components: { ButtonCalc, DisplayCalc },
    methods: {
        clearMemory() {
            Object.assign(this.$data, this.$options.data())
        },
        setOperation(operation) {
            console.log(operation)
        },
        addDigit(n) {
            if(n === "." && this.displayValue.includes(".")) {
                return
            }

            const clearDisplay = this.displayValue === "0"
                || this.clearDisplay
            const currentValue = clearDisplay ? "" : this.displayValue
            const displayValue = currentValue + n

            this.displayValue = displayValue
            this.clearDisplay = false

            if(n !== ".") {
                const i = this.current
                const newValue = parseFloat(displayValue)
                this.values[i] = newValue
            }
        }
    }
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