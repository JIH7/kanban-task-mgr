<svelte:head>
    <title>Task Tracker</title>
</svelte:head>
<AddTask />
<Header data={Data} currentBoard={currentBoard} />
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
</script>