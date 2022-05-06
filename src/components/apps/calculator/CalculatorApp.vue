<template>
  <div class="calculator-app">
    <p class="calculator-app__display">{{displayedValue}}</p>
    <div class="calculator-app__keyboard">
      <div class="calculator-app__button" @click="clear">C</div>
      <div class="calculator-app__button">+/-</div>
      <div class="calculator-app__button" @click="addSymbol('%')">%</div>
      <div class="calculator-app__button calculator-app__button_highlighted" @click="addSymbol('/')">÷</div>
      <div class="calculator-app__button" @click="addSymbol('1')">1</div>
      <div class="calculator-app__button" @click="addSymbol('2')">2</div>
      <div class="calculator-app__button" @click="addSymbol('3')">3</div>
      <div class="calculator-app__button calculator-app__button_highlighted" @click="addSymbol('*')">X</div>
      <div class="calculator-app__button" @click="addSymbol('4')">4</div>
      <div class="calculator-app__button" @click="addSymbol('5')">5</div>
      <div class="calculator-app__button" @click="addSymbol('6')">6</div>
      <div class="calculator-app__button calculator-app__button_highlighted" @click="addSymbol('-')">-</div>
      <div class="calculator-app__button" @click="addSymbol('7')">7</div>
      <div class="calculator-app__button" @click="addSymbol('8')">8</div>
      <div class="calculator-app__button" @click="addSymbol('9')">9</div>
      <div class="calculator-app__button calculator-app__button_highlighted" @click="addSymbol('+')">+</div>
      <div class="calculator-app__button calculator-app__button_double-sized" @click="addSymbol('0')">0</div>
      <div class="calculator-app__button" @click="addSymbol('.')">,</div>
      <div class="calculator-app__button calculator-app__button_highlighted" @click="calculateResult">=</div>
    </div>
  </div>
</template>

<script>
export default {
  name: "CalculatorApp",
  data: function () {
    return {
      displayedValue: "123"
    }
  },
  methods: {
    addSymbol: function (symbol) {
      this.displayedValue += symbol;
    },
    clear: function() {
      this.displayedValue = "";
    },
    calculateResult: function () {
      this.displayedValue = eval(this.displayedValue);
    }
  }
}
</script>

<style lang="scss" scoped>
.calculator-app {
  display: flex;
  flex-direction: column;
  justify-content: flex-end;

  height: 100%;

  box-sizing: border-box;
  padding: .25vw;
  padding-top: 3vw;
  padding-bottom: 2.5vw;

  background-color: black;

  &__display {
    font-size: 3vw;
    font-weight: 500;
    text-align: right;
  }

  &__keyboard {
    display: grid;
    grid-template-columns: repeat(4, 1fr);
    gap: .2vw;

    width: 100%;
  }

  &__button {
    display: flex;
    align-items: center;
    justify-content: center;

    width: 3.5vw;
    height: 3.5vw;

    font-size: 2vw;
    font-weight: 500;

    background-color: #979797;
    border-radius: 100vw;

    &_highlighted {
      background-color: #FF8933;
    }

    &_double-sized {
      grid-column: span 2;
      justify-content: start;

      width: 100%;

      box-sizing: border-box;
      padding: 0 1.25vw;
    }
  }
}
</style>