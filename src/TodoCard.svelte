<script>
  export let todo;
  export let removeTodo;
</script>

<li>
  <input type="checkbox" bind:checked={todo.isDone} />
  <span class={`${todo.isDone && "checked"}`}>{todo.title}</span>
  {#if todo.isDone}
    <button on:click={removeTodo(todo.id)}>削除</button>
  {/if}
</li>

<style>
  li {
    list-style: none;
  }
  .checked {
    color: gray;
  }
</style>
