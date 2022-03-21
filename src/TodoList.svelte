<script>
  import { todos } from "./store";
</script>

{#each $todos as todo (todo.id)}
  <div>
    <input type="checkbox" id="todo-{todo.id}" checked={todo.isCompleted} />
    <label for="todo-{todo.id}">{todo.job}</label>
  </div>
{/each}

<style>
</style>
