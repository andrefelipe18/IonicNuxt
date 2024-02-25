<script setup>
const num1 = ref(0);
const num2 = ref(0);
const result = ref(0);

const soma = () => {
	result.value = Number(num1.value) + Number(num2.value);
	num1.value = '';
	num2.value = '';
};

const subtracao = () => {
	result.value = Number(num1.value) - Number(num2.value);
	num1.value = '';
	num2.value = '';
};

const multiplicacao = () => {
	result.value = Number(num1.value) * Number(num2.value);
	num1.value = '';
	num2.value = '';
};

const divisao = () => {
	result.value = Number(num1.value) / Number(num2.value);
	num1.value = '';
	num2.value = '';
};
</script>
<template>
	<div class="flex flex-col justify-center items-center">
		<h1>Index</h1>
		<label class="form-control w-full max-w-xs">
			<div class="label">
				<span class="label-text">Número 1</span>
			</div>
			<input v-model="num1" type="number" placeholder="" class="input input-bordered input-primary w-full max-w-xs" />
		</label>

		<label class="form-control w-full max-w-xs">
			<div class="label">
				<span class="label-text">Número 2</span>
			</div>
			<input v-model="num2" type="number" placeholder="" class="input input-bordered input-primary w-full max-w-xs" />
		</label>

		<div class="join my-12">
			<button @click="soma" class="btn btn-info join-item">Soma</button>
			<button @click="subtracao" class="btn btn-success join-item">Subtração</button>
			<button @click="multiplicacao" class="btn btn-warning join-item">Multiplicação</button>
			<button @click="divisao" class="btn btn-error join-item">Divisão</button>
		</div>

		<h2>Result: {{ result }}</h2>
		<NuxtLink to="/users">Users</NuxtLink>
	</div>
</template>
<style scoped></style>