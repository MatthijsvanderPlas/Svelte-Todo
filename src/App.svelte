<script>
  import Header from "./lib/Header.svelte"

  let todos = [];

  function handleTodo(event) {
    todos = [...todos, event.detail.text]
  }
</script>

<main>
  <div class="card">
    <Header on:todo={handleTodo}/>
    <ul>
      {#each todos as todo}
       <li>{todo}</li>
       {/each}    
    </ul>
  </div>
  
  
</main>

<style>
  .card {
    width: 80%;
    min-width: 300px;
    height: auto;
    min-height: 250px;
    background-color: #f9f9f9;
    border: 1px solid black;
    border-radius: 15px;
    box-shadow: 1px 1px 6px rgba(0, 0, 0, 0.25);
    padding: 1rem;
  }
</style>
