<section class="task-column">
    <h3><div></div><span>{name}</span></h3>
    <div use:dndzone>
        {#each tasks as {title, subtasks}}
            <TaskWidget task={title} totalSubtasks={subtasks.length} />
        {/each}
    </div>
</section>

<script>
    import TaskWidget from "./TaskWidget.svelte";
    import { dndzone } from 'svelte-dnd-action';

    export let name;
    export let tasks;
</script>