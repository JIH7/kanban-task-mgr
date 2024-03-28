<section class="task-column">
    <h3><div></div><span>{name}</span></h3>
    <div use:dndzone={{ items: localTasks, type: 'TASK' }} on:consider={handleDrop} on:finalize={handleDrop}>
        {#each localTasks as task (task.id)}
            <TaskWidget task={task.title} totalSubtasks={task.subtasks.length} />
        {/each}
    </div>
</section>

<script>
    import TaskWidget from "./TaskWidget.svelte";
    import { dndzone } from 'svelte-dnd-action';
    import { createEventDispatcher } from "svelte";

    const dispatch = createEventDispatcher();

    export let name;
    export let tasks;
    export let columnID;

    let localTasks = tasks.map((task, index) => ({ id: index, ...task }));

    function handleDrop(event) {
        localTasks = event.detail.items;
        
        let updatedTasks = localTasks.map(({ id, ...task }) => task)

        dispatch('updateTasks', updatedTasks);
    }
</script>