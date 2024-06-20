<script lang="ts">
    import Todo from "$lib/Todo.svelte"
    let incompleteTodos: string[] = [];
    let completeTodos: string[] = []; 

    let currentTodo: string;

    function addTodo() {
        incompleteTodos = [currentTodo, ...incompleteTodos];
    }
</script>

<div class="px-3 py-2 flex flex-col gap-4">
    <h1 class="text-3xl font-semibold">To-Dos</h1>

    <div class="p-2 flex gap-2 bg-gray-400 rounded-md">
        <input type="text" name="Todo" class="bg-slate-500 p-2 rounded-md shadow-sm" bind:value={currentTodo}>
        <button on:click={addTodo} disabled={currentTodo === ""} class="bg-slate-500 p-2 rounded-md shadow-sm">Add</button>
    </div>

    {#each incompleteTodos as todo}
        <Todo {todo}/>
    {/each}
</div>