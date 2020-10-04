<script>
    import Card from "./Card.svelte";
    import Filters from "./Filters.svelte";
    import Manage from "./Manage.svelte";

    function filterData(event) {
        console.log(event.detail);
        // Show all data
        if (event.detail === 'all') {
            filteredContent = todos;
        // Only show completed items
        } else if (event.detail === 'complete') {
            filteredContent = todos.filter(item => item.completed);
        // Only show incomplete items
        } else {
            filteredContent = todos.filter(item => !item.completed);
        }
    }

    function updateList(event) {
        console.log(event, todos);
        if (event.detail != "") {
            todos.unshift({
                "completed": false,
                "id": todos.length + 1,
                "title": event.detail
            });
            filteredContent = todos;
        }
    }

    export let todos;
    export let filteredContent = todos;
</script>

<div>
    <Filters on:updatefilter={ filterData } />
    <Manage on:updateTodos={ updateList } />
</div>
<ul>
    {#each filteredContent as todo}
        <Card data={ todo } />
    {/each}
</ul>

<style>
    div {
        display: flex;
        justify-content: space-between;
        margin-bottom: 2rem;
    }
</style>