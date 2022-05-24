<script>
  import { todos } from "./store";

  $: notCompletedTodos = $todos.filter((todo) => !todo.isCompleted);
  $: completedTodos = $todos.filter((todo) => todo.isCompleted);

  const handleCheck = (id) => {
    $todos = $todos.map((todo) => {
      return {
        ...todo,
        isCompleted: todo.id === id ? !todo.isCompleted : todo.isCompleted,
      };
    });
  };

  $: console.log($todos);
</script>

<h2>Todos</h2>
{#each notCompletedTodos as todo (todo.id)}
  <div>
    <input
      type="checkbox"
      id="todo-{todo.id}"
      checked={todo.isCompleted}
      on:click={() => handleCheck(todo.id)}
    />
    <label for="todo-{todo.id}">{todo.job}</label>
  </div>
{/each}

<h2>Completed Todos</h2>
{#each completedTodos as todo (todo.id)}
  <div>
    <ul>
      <li>{todo.job}</li>
    </ul>
  </div>
{/each}
