<script>
    import TodoInput from "./TodoInput.svelte"
</script>

<div>
    <h1>
        Todo-App
    </h1>
    <TodoInput on:todo/>
</div>

<style>
    h1 {
        font-size: 1.5rem;
        color: rgb(196, 0, 105);
    }
</style>