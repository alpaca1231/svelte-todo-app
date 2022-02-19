<script>
  import TodoList from './TodoList.svelte';
  import InputForm from './InputForm.svelte';

  export let todos = [
    { id: 0, title: 'SvelteでHelloWord', isDone: false },
    { id: 1, title: 'SvelteでTodoアプリ', isDone: false },
  ];

  export const addTodo = (newTodo) => {
    console.log(todos);
    console.log(newTodo);
    todos = [...todos, { id: todos.length, title: newTodo, isDone: false }];
  };

  export const removeTodo = (id) => {
    console.log(todos);
    todos = todos.filter((todo) => id !== todo.id);
    todos = todos.map((todo) => {
      return { id: todos.length, title: todo.newTodo, isDone: todo.isDone };
    });
  };
</script>

<main>
  <h1>Svelte Todo リスト</h1>
  <TodoList bind:todos {removeTodo} />
  <InputForm {addTodo} />
</main>

<style>
  h1 {
    color: #ff3e00;
    text-transform: uppercase;
    font-size: 4em;
    font-weight: 100;
  }
</style>
