<svelte:head>
    <title>Task Tracker</title>
</svelte:head>
<Header />
<Main  data={Data}/>


<style>
    @import '../lib/styles/style.css';
</style>

<script>
    import Header from '../lib/components/header.svelte';
    import Main from '../lib/components/Main.svelte';

    import Data from '../data.json';
</script>