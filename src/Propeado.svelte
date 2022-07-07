<script>
    export let number = 0;
    let todos = []

    let todo = ''

    const submitTodo = (e) => {
        todos = [...todos, todo]
        todo = ''
    }
    const deleteTodo = (todoItem) => {
        todos = todos.filter(td => td !== todoItem)
    }
</script>

<div>
    {number}
    <ul>
        {#each todos as item}
        <li on:click={()=>deleteTodo(item)}>
            {item}
        </li>
        {/each}
    </ul>

    <form on:submit|preventDefault={submitTodo}>
        <input type="text" bind:value={todo}>
        <button type="submit">Submit Todo</button>
    </form>
</div>