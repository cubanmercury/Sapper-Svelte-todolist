<script>
    import { createEventDispatcher } from 'svelte';
    const dispatch = createEventDispatcher();

    let item = "";

    function addTodo(event) {
        dispatch('updateTodos', item);
    }

</script>

<div>
    <label for="add-todo">Add todo:</label>
    <input id="add-todo" bind:value={item} on:change={ addTodo }>
</div>

<style>
    input {
        width: 100%;
    }
</style>