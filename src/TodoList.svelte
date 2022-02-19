<script>
  import TodoCard from "./TodoCard.svelte";
  export let todos;
  export let removeTodo;
</script>

<ul>
  {#each todos as todo}
    <TodoCard {todo} {removeTodo} />
  {/each}
</ul>
