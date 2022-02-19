<script>
  let newTodo = "";
  export let addTodo;

  const submit = (e) => {
    e.preventDefault();
    if (!newTodo) return;
    addTodo(newTodo);
    newTodo = "";
  };
</script>

<form on:submit={submit}>
  <input type="text" bind:value={newTodo} />
  <button on:click={submit}>追加</button>
</form>

<style>
</style>
