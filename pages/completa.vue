<script setup>
const display = ref('');

const handleKey = (key) => {
  display.value += key;
};

const clear = () => {
  display.value = '';
};

const clearLast = () => {
  display.value = display.value.slice(0, -1);
};

const calculate = () => {
  display.value = eval(display.value);
};
</script>
<template>
  <ion-page>
    <div class="flex flex-col justify-center items-center">
      <h1>Calc Completa - <NuxtLink to="/">Index</NuxtLink>
      </h1>

      <div class="">
        <input type="text" v-model="display" disabled class="input input-bordered input-primary w-full max-w-xs" />
      </div>

      <div class="flex flex-col gap-2 mt-5">
        <div class="flex gap-x-1">
          <kbd class="kbd h-20 w-20" @click="clear()">C</kbd>
          <kbd class="kbd h-20 w-20" @click="clearLast()">CE</kbd>
          <kbd class="kbd h-20 w-20" @click="handleKey('%')">%</kbd>
          <kbd class="kbd h-20 w-20" @click="handleKey('/')">/</kbd>
        </div>

        <div class="flex gap-x-2">
          <kbd class="kbd h-20 w-20" @click="handleKey('7')">7</kbd>
          <kbd class="kbd h-20 w-20" @click="handleKey('8')">8</kbd>
          <kbd class="kbd h-20 w-20" @click="handleKey('9')">9</kbd>
          <kbd class="kbd h-20 w-20" @click="handleKey('*')">*</kbd>
        </div>

        <div class="flex gap-x-2">
          <kbd class="kbd h-20 w-20" @click="handleKey('4')">4</kbd>
          <kbd class="kbd h-20 w-20" @click="handleKey('5')">5</kbd>
          <kbd class="kbd h-20 w-20" @click="handleKey('6')">6</kbd>
          <kbd class="kbd h-20 w-20" @click="handleKey('-')">-</kbd>
        </div>

        <div class="flex gap-x-2">
          <kbd class="kbd h-20 w-20" @click="handleKey('1')">1</kbd>
          <kbd class="kbd h-20 w-20" @click="handleKey('2')">2</kbd>
          <kbd class="kbd h-20 w-20" @click="handleKey('3')">3</kbd>
          <kbd class="kbd h-20 w-20" @click="handleKey('+')">+</kbd>
        </div>

        <div class="flex gap-x-2">
          <kbd class="kbd h-20 w-20">+/-</kbd>
          <kbd class="kbd h-20 w-20" @click="handleKey('0')">0</kbd>
          <kbd class="kbd h-20 w-20" @click="handleKey('.')">.</kbd>
          <kbd class="kbd h-20 w-20 bg-blue-400 text-white" @click="calculate()">=</kbd>
        </div>
      </div>

      <h2>Result</h2>
      <NuxtLink to="/completa">Ir para calculadora simples</NuxtLink>
    </div>
  </ion-page>
</template>
<style scoped></style>