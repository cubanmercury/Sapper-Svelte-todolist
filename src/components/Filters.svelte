<script>
    import { createEventDispatcher } from 'svelte';

    const dispatch = createEventDispatcher();

    let selected = 'all';
    
    function updateFilter(event) {
        dispatch('updatefilter', selected);
    }
</script>


<div>
	<label for="filter">Filter:</label>
    <select id="filter" bind:value={ selected } on:change={ updateFilter }>
        <option value="all">All</option>
        <option value="incomplete">Incomplete</option>
        <option value="complete">Complete</option>
    </select>
</div>

<style>
	label {
		font-size: 1rem;
	}

    div {
        width: 330px;
    }

    select {
        width: 100%;
    }
</style>

