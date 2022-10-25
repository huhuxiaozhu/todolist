<template>
	<div class="todo-underway todolist-container">
		<div class="todolist-header-container">
			<h2>正在进行</h2>
			<div class="todo-count">{{todolists.length}}</div>
		</div>
		<div class="todo-underway-items">
			<transition-group enter-active-class="animate__animated animate__fadeIn" leave-active-class="animate__animated animate__fadeOut">
				<Item v-for="(item,index) of todolists" :key="item.id" :content="item.content" :index="index"
					@dele="del" @click="finish" />
			</transition-group>
		</div>
	</div>
</template>

<script>
	import Item from './Item.vue';
	export default {
		props: ["todolists"],
		components: {
			Item
		},
		methods: {
			del(index) {
				this.todolists.splice(index, 1);
			},
			finish(index) {
				let item = this.todolists.splice(index, 1)[0];
				this.$emit("click", item);
			}
		}
	}
</script>

<style scoped>
	.todolist-header-container {
		display: flex;
		justify-content: space-between;
		align-items: center;
	}

	.todo-count {
		display: inline-block;
		padding: 0 5px;
		height: 20px;
		border-radius: 20px;
		background: #E6E6FA;
		line-height: 22px;
		text-align: center;
		color: #666;
		font-size: 14px;
	}

	/* .todolist-container{
		height: 60px;
		display: flex;
		justify-content: space-between;
		align-items: center;
	} */
	/* h2{
		width: 200px;
		height: 100%;
		line-height: 60px;
	}
	.todo-count{
		width: 30px;
		height: 30px;
		line-height: 30px;
		text-align: center;
		background-color:red;
		border-radius: 50%;
	} */
</style>
