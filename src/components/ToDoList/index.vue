<template>
	<div>
		<to-do-header @addTodo="addTodo"></to-do-header>
		<under-way :todolists="todolists" @click="finish"></under-way>
		<completed :todolists="finishlists" @click="todo"></completed>
	</div>
</template>

<script>
	// EventBus
	import ToDoHeader from './Header.vue';
	import UnderWay from './Underway.vue';
	import Completed from './Completed.vue';
	export default {
		components: {
			ToDoHeader,
			UnderWay,
			Completed
		},
		data(){
			return {
				todolists: [],
				finishlists:[]
			}
		},
		methods:{
			addTodo(obj){
				this.todolists.push(obj);
			},
			finish(item){
				this.finishlists.push(item);
			},
			todo(item) {
				this.todolists.push(item);
			}
		}
	}
</script>

<style>
	.todolist-container{
		width: 1000px;
		/* background-color: black; */
		margin: auto;
	}
</style>
