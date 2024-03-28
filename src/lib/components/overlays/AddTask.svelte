<Backdrop />
<div class="overlay-menu-container">
    <section class="overlay-menu">
        <h2>Add Task</h2>
        <form action="" on:submit={handleSubmit}>
            <label for="task-name">Task Name</label>
            <input type="text" name="task-name" id="task-name" placeholder="e.g. Take coffee break">
            <label for="description">Description</label>
            <textarea name="description" id="description" placeholder="e.g. It’s always good to take a break. This 15 minute break will  recharge the batteries a little."></textarea>
            <p>Subtasks</p>
            <ul>
                {#each subtasks as subtask, index}
                    <SubtaskInput on:change={({detail}) => {subtasks[detail.index] = detail.subtask} } index={index} removeSubtask={removeSubtask} subtask={subtasks[index]}/>
                {/each} 
            </ul>
            <button type="button" on:click={addSubtask}>+Add Subtask</button>
            <label for="status-select">Status</label>
            <select name="status-select" id="status-select">
                {#each data.boards[currentBoard].columns as column, i}
                    <option value={column.name}>{column.name}</option>
                {/each}
            </select>
            <button class="submit-button" type="submit">Create Task</button>
        </form>
    </section>
</div>

<script>
    import Backdrop from "./Backdrop.svelte";
    import SubtaskInput from "./SubtaskInput.svelte";

    export let data = null;
    export let currentBoard;
    export let subtasks = [''];

    function addSubtask() {
        subtasks.push("");
        subtasks = subtasks;
    }

    function removeSubtask(index) {
        if (subtasks.length > 1)
            subtasks = subtasks.filter((subtask, i) => i !== index);
        else
            subtasks = [''];
    }

    import { createEventDispatcher } from 'svelte';
    const dispatch = createEventDispatcher();

    function handleSubmit(event) {
        event.preventDefault();

        // Convert subtasks array to an array of objects
        const subtasksObj = subtasks.map((subtasks) => ({
                name: subtasks,
                isCompleted: false
        }))

        const newTask = {
            title: event.target['task-name'].value,
            description: event.target['description'].value,
            subtasks: subtasksObj,
            status: event.target['status-select'].value
        };

        dispatch('addTask', newTask);
    }
</script>