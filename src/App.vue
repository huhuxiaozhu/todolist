<template>
	<div id="app">
		<to-do-list></to-do-list>
	</div>
</template>

<script>
	import ToDoList from './components/ToDoList/index.vue'
	export default {
		name: "App",
		components: {
			ToDoList
		}
	}
</script>

<style>
	body,
	html {
		background-color: #cdcdcd;
	}
</style>
