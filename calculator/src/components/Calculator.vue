<template>
  <div class="main-container">
    <h1>Calculator</h1>
    <h2>Test</h2>
    <div class="output">
      <p>{{ displayOutput }}</p>
    </div>

    <div class="operations">
      <button @click="clearDisplay" class="operation">AC</button>
      <button @click="deleteDigit()" class="operation">DEL</button>
      <button @click="appendToDisplay('/')" class="operation">/</button>
      <button @click="appendToDisplay('-')" class="operation">-</button>
    </div>

    <div class="numpad-row-1">
      <button @click="appendToDisplay('7')" class="numpad-button">7</button>
      <button @click="appendToDisplay('8')" class="numpad-button">8</button>
      <button @click="appendToDisplay('9')" class="numpad-button">9</button>
      <button @click="appendToDisplay('*')" class="operation">*</button>
    </div>

    <div class="numpad-row-2">
      <button @click="appendToDisplay('4')" class="numpad-button">4</button>
      <button @click="appendToDisplay('5')" class="numpad-button">5</button>
      <button @click="appendToDisplay('6')" class="numpad-button">6</button>
      <button @click="appendToDisplay('+')" class="operation">+</button>
    </div>

    <div class="numpad-row-3">
      <button @click="appendToDisplay('0')" class="numpad-button">0</button>
      <button @click="appendToDisplay('1')" class="numpad-button">1</button>
      <button @click="appendToDisplay('2')" class="numpad-button">2</button>
      <button @click="appendToDisplay('3')" class="numpad-button">3</button>
    </div>

    <div class="numpad-row-4">
      <button @click="appendToDisplay('.')" class="numpad-button">.</button>
      <button @click="calculate()" class="numpad-button">=</button>
    </div>
  </div>
</template>

<script setup>
import { ref } from "vue";

let displayOutput = ref("");

const appendToDisplay = (input) => {
  displayOutput.value += input;
};

const clearDisplay = () => {
  displayOutput.value = "";
};

const calculate = () => {
  try {
    const result = eval(displayOutput.value);
    displayOutput.value = result;
  } catch (err) {
    displayOutput.value = "Error";
  }
};

const deleteDigit = () => {
  try {
    const deleted = displayOutput.value.slice(0, -1);
    displayOutput.value = deleted;
  } catch {
    displayOutput.value = "Error";
  }
};
</script>

<style>
.numpad-row-4 {
  text-align: left;
  margin-left: 47.5px;
}
h1 {
  color: whitesmoke;
}
body {
  background: #101320;
}
.numpad-button {
  height: 50px;
  width: 50px;
  padding: 10px;
  margin: 3px;
  border-radius: 50px;
  background: white;
  cursor: pointer;
  border: none;
}
.numpad-button:hover {
  background-color: #666;
}

.operation:hover {
  background-color: #666;
}
.operation {
  height: 50px;
  width: 50px;
  padding: 10px;
  margin: 3px;
  border-radius: 50px;
  background: rgb(145, 140, 140);
  cursor: pointer;
  border: none;
}

.main-container {
  background: black;
  width: 320px;
  height: 400px;
  margin: 0px auto;
  border-radius: 30px;
  padding: 25px;
  box-shadow: rgba(0, 0, 0, 0.35) 0px 5px 15px;
}

.output {
  background: black;
  height: 50px;
  border: none;
  border-radius: 50px;
  margin-bottom: 10px;
  align-items: center;
  display: flex;
}

.output p {
  margin: 0px auto;
  color: white;
}
</style>
