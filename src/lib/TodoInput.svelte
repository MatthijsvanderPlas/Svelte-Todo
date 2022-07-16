<script>
    import { createEventDispatcher } from "svelte";
    let todo = '';
    const dispatch = createEventDispatcher();
    function addTodoItem() {
        dispatch('todo', {
            text: todo
        });
        todo = ''
    }
</script>

<form on:submit|preventDefault={addTodoItem}>
    <input type="text" bind:value={todo} id="todo" placeholder="Add Todo Item">
    <button disabled={!todo} type="submit">
        Add
    </button>
</form>

<style>
    form {
        display: flex;
        justify-content: space-between;
        align-items: baseline;
    }

    input[type="text"] {
        width: 80%;
        height: 35px;
        font-size: 1.25rem;
        padding: 0.25rem;
        margin: 1rem;
    }

    button {
        width: 10rem;
        height: 50px;
        background: none;
        font-size: 1.25rem;
        font-weight: 700;
        color: white;
        background-color:  rgb(196, 0, 105);
        margin: 1rem;
        padding: .35rem;
        border: 1px solid black;
        cursor: pointer;
        border-radius: 5px;
        transition: all 300ms ease-in-out;
    }

    button:hover {
        box-shadow: 1px 1px 5px rgba(0, 0, 0, 0.25);
    }

    button:disabled {
        width: 10rem;
        background: none;
        font-size: 1.25rem;
        font-weight: 700;
        color: white;
        background-color:  rgba(196, 0, 105, 0.25);
        padding: .35rem;
        border: 1px solid white;
        cursor: none;
        border-radius: 5px;
    }
</style>