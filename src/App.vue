<template>
 <div>
	<h1>Witaj w systemie do zapisów na zajęcia</h1>
	<div v-if="authenticated"> 
	<h4> Witaj {{email}}</h4>
	
	<a @click="logOut()"> Wyloguj</a>
	</div>
	<div v-else>
		Zaloguj się emailem
		<input type="email" v-model="email">
		<button @click="logIn()">Wchodzę!</button>
	</div>


 </div>
</template>

<script>


export default {
	data() {
		return {
			authenticated: false,
			email: ''
		};
	},
	methods: {
		logIn() {
			this.authenticated= true;
		}, 
		logOut() {
			this.authenticated= false;
			this.email = '';
		}
	}
}
</script>

<style>
a {
color: green
}
</style>
