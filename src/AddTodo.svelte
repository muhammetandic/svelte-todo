<script>
  import { todos } from "./store";

  let newId;
  $: {
    if ($todos.length === 0) {
      newId = 1;
    } else {
      newId = Math.max(...$todos.map((item) => item.id)) + 1;
    }
  }

  let newTodo = "";
  const addTodo = () => {
    $todos = [...$todos, { id: newId, job: newTodo, isCompleted: false }];
    newTodo = "";
  };
</script>

<div>
  <form on:submit|preventDefault={addTodo}>
    <input type="text" name="todo" bind:value={newTodo} autocomplete="off" />
    <input type="submit" value="Add" />
  </form>
</div>

<style>
  div {
    text-align: center;
  }
</style>
