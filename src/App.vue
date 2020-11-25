<template>
	<div id="app">
		<div id="nav">
			<h2>
        <router-link to="/">Home</router-link> | <router-link to="/about">About</router-link>
      </h2>
		</div>
		<router-view />
	</div>
</template>

<style>
html {
	background-image: url('https://res.cloudinary.com/mokaweb/image/upload/v1606235303/Jokes_API/dinocorn.jpg');
	height: 100vh;
	background-repeat: no-repeat;
	background-size: cover;
	background-position: bottom;
	color: rgb(255, 253, 247);
}

#app {
	font-family: Avenir, Helvetica, Arial, sans-serif;
	-webkit-font-smoothing: antialiased;
	-moz-osx-font-smoothing: grayscale;
}

#nav {
	text-align: right;
	padding: 10px;
  margin-right: 1%;
}

#nav a {
	font-weight: bold;
	color: rgb(255, 253, 247);
}

#nav a.router-link-exact-active {
	color: #f5ec05;
}
</style>
