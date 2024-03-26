<main>
    {#if data === null}
        <EmptyBoard />
    {:else}
        {#each data.boards[0].columns as {name, tasks}, i}
            <Column name={name} tasks={tasks}/>
        {/each}
    {/if}
</main>

<script>
    
    import EmptyBoard from "./main/EmptyBoard.svelte";
    import Column from "./main/Column.svelte";
    
    export let data;
</script>