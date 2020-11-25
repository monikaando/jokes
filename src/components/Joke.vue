<template>
	<div>
		<h1>{{ joke.setup }}</h1>
		<h2>{{ joke.punchline }}</h2>
		<button class="btn yellow" @click="$emit('get-joke')">Next</button>	
	</div>
</template>

<script>
export default {
	name: 'Joke',
	props: ['joke'],
};
</script>

<style scoped>

</style>
