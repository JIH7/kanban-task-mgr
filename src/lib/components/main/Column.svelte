<section class="task-column">
    <h3><div></div><span>{name}</span></h3>
    {#each tasks as {title, subtasks}}
        <TaskWidget task={title} totalSubtasks={subtasks.length} />
    {/each}
</section>

<script>
    import TaskWidget from "./TaskWidget.svelte";

    export let name;
    export let tasks;
</script>