<main>
    {#if data === null}
        <EmptyBoard />
    {:else}
        {#each data.boards[currentBoard].columns as {name, tasks}, i}
            <Column name={name} tasks={tasks} on:updateTasks={handleUpdateTasks}/>
        {/each}
    {/if}
</main>

<script>
    import EmptyBoard from "./main/EmptyBoard.svelte";
    import Column from "./main/Column.svelte";

    export let data;
    export let currentBoard;

    function handleUpdateTasks(event) {
        console.log(event.detail);
    }
</script>