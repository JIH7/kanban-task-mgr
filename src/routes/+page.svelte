<svelte:head>
    <title>Task Tracker</title>
</svelte:head>
{#if showAddTask}
    <AddTask data={Data} currentBoard={currentBoard} on:addTask={handleSubmitTask}/>
{/if}
<Header data={Data} currentBoard={currentBoard} on:showAddTask={handleAddTask} />
<Main  data={Data} currentBoard={currentBoard}/>


<style>
    @import '../lib/styles/style.css';
</style>

<script>
    import Header from '../lib/components/header.svelte';
    import Main from '../lib/components/Main.svelte';

    import Data from '../data.json';
    import AddTask from '../lib/components/overlays/AddTask.svelte';

    let currentBoard = 0;
    let showAddTask = false;

    function handleAddTask() {
        showAddTask = true;
    }

    function handleSubmitTask(event) {
        const task = event.detail;
        Data.boards[currentBoard].columns[0].tasks.push(task);
        Data.boards[currentBoard] = Data.boards[currentBoard];
        showAddTask = false;
    }
</script>