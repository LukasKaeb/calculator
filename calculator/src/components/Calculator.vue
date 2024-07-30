<template>
    
<div class="main-container">
    <h1>Calculator</h1>
    <div class="output">
        <p>Output</p>
    </div>

    <div class="operations">
        <button class="operation">AC</button>
        <button class="operation">DEL</button>
        <button class="operation">/</button>
        <button class="operation">-</button>
    </div>

    <div class="numpad-row-1">
        <button class="numpad-button">7</button>
        <button class="numpad-button">8</button>
        <button class="numpad-button">9</button>
        <button class="operation">*</button>
    </div>

    <div class="numpad-row-2">
        <button class="numpad-button">4</button>
        <button class="numpad-button">5</button>
        <button class="numpad-button">6</button>
        <button class="operation">+</button>

    </div>
    
    <div class="numpad-row-3">
        <button class="numpad-button">0</button>
        <button class="numpad-button">1</button>
        <button class="numpad-button">2</button>
        <button class="numpad-button">3</button>
    </div>

</div>

</template>

<script setup>

</script>

<style>
h1{
    color: whitesmoke;
}
body{
    background: #101320;
}
.numpad-button{
    height: 50px;
    width: 50px;
    padding: 10px;
    margin: 3px;
    border-radius: 50px;
    background: white;
    cursor: pointer;
    border: none;
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

.main-container{
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