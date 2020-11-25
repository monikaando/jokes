<template>
	<div class="jokes">
		<Joke class="joke" v-bind:joke="joke" v-on:get-joke="getJoke" />
		<NorrisJoke class="joke" v-bind:norrisJoke="norrisJoke" v-on:get-norris-joke="getNorrisJoke" />
	</div>
</template>

<script>
// @ is an alias to /src
import Joke from '@/components/Joke';
import NorrisJoke from '@/components/NorrisJoke';
import axios from 'axios';

export default {
	name: 'Home',
	components: {
		Joke,
		NorrisJoke,
	},
	data() {
		return {
			joke: {},
			norrisJoke: {},
		};
	},
	methods: {
		getJoke() {
			axios
				.get('https://official-joke-api.appspot.com/jokes/random')
				.then((res) => (this.joke = res.data))
				.catch((err) => console.log(err));
		},
		getNorrisJoke() {
			axios
				.get('https://api.icndb.com/jokes/random')
				.then((res) => (this.norrisJoke = res.data.value))
				.catch((err) => console.log(err));
		},
	},
	created() {
		this.getJoke(), this.getNorrisJoke();
	},
};
</script>
<style>
.jokes {
	display: flex;
	flex-direction: row;
	justify-content: space-between;
	align-items:flex-end;
	height: 55vh;
	margin: 0 3%;
}
.joke {
	width: 30%;
}

.btn {
  border-radius: 5px;
  padding: 15px 25px;
  font-size: 22px;
  text-decoration: none;
  border:none;
  margin: 20px 0;
  color: #fff;
  position: relative;
  display: inline-block;
  width: 40%;
}
.btn:active {
  transform: translate(0px, 5px);
  -webkit-transform: translate(0px, 5px);
  box-shadow: 0px 1px 0px 0px;
}
.yellow {
  background-color: #f1c40f;
  box-shadow: 0px 5px 0px 0px #D8AB00;
}

.yellow:hover {
  background-color: #f5ec05;;
}
.pink {
  background-color: #d61fb2;
  box-shadow: 0px 5px 0px 0px #e96ad0;
}

.pink:hover {
  background-color:  #f85cd9;
}

</style>
