<li>
    <input on:change={handleChange} value={subtask} type="text" name="subtask-{index}" id="subtask-{index}">
    <button on:click={() => {removeSubtask(index);}}><img src={Cross} alt="cross"></button>
</li>

<script>
    import { createEventDispatcher } from 'svelte';
    import Cross from '../../assets/icon-cross.svg';

    const dispatch = createEventDispatcher();

    export let index = 0;
    export let removeSubtask = () => {};
    export let subtask = '';

    function handleChange(event) {
        subtask = event.target.value;
        dispatch('change', {index, subtask});
    }
</script>