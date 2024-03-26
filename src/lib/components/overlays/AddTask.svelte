<Backdrop />
<div class="overlay-menu-container">
    <section class="overlay-menu">
        <h2>Add Task</h2>
        <form action="">
            <label for="task-name">Task Name</label>
            <input type="text" name="task-name" id="task-name" placeholder="e.g. Take coffee break">
            <label for="description">Description</label>
            <textarea name="description" id="description" placeholder="e.g. It’s always good to take a break. This 15 minute break will  recharge the batteries a little."></textarea>
        </form>
    </section>
</div>

<script>
    import Backdrop from "./Backdrop.svelte";
</script>