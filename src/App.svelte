<script>
	import TodoList from "./TodoList.svelte";
	import AddTodo from "./AddTodo.svelte";
	import { todos } from "./store";

	$todos = [
		{
			id: 1,
			job: "Learn Svelte",
			isCompleted: true,
		},
		{
			id: 2,
			job: "become expert on react",
			isCompleted: false,
		},
	];
</script>

<main>
	<h1>Svelte Todo App</h1>
	<AddTodo />
	<TodoList />
</main>

<style>
	main {
		padding: 0em;
		width: 500px;
		margin: 0 auto;
	}

	h1 {
		color: #23c9f3;
		text-transform: uppercase;
		font-size: 3em;
		font-weight: 100;
		text-align: center;
	}
</style>
