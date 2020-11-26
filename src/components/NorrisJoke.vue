<template>
	<div>
		<h1>{{ norrisJoke.joke }}</h1>
		<button class="btn pink" @click="$emit('get-norris-joke')">Next</button>
	</div>
</template>

<script>
export default {
	name: 'NorrisJoke',
	props: ['norrisJoke'],
};
</script>

<style scoped></style>
