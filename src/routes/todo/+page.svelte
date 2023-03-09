<script>
    import { bind } from "svelte/internal";
    import "../../app.css";


    let todos = []
    let bindtodo
    function todoAdd(){
        todos.push(bindtodo)
        todos = todos
        bindtodo = ""
    }
    function todoRem(id){
        let index = todos.indexOf(id);
        if (index !== -1) {
            todos.splice(index, 1);
            todos = todos;
        }
    }
    function todoEmpty(){
        todos = []
        todos = todos
    }

</script>
<div class="p-5">
    <ul>
        <!-- Todos here-->
        {#each todos as todo}
            <todo id={todo}>
                <button class="inline-block remove-button" on:click={todoRem(todo)}>X</button>
                <li class="inline-block">{todo}</li>
            </todo>
        {/each}
    </ul>
    <form id="inputform" onsubmit="preventDefault();" class="pt-5">
        <input id="inputtodo" type="text" placeholder="Item text..." class="bg-gray-50 border border-gray-300 text-gray-900 text-sm rounded-lg focus:ring-blue-500 focus:border-blue-500  p-2.5" bind:value={bindtodo}>
        <button id="submitbutton" class="text-white bg-red-600 hover:bg-red-700 focus:outline-none focus:ring-4 focus:ring-red-300 font-medium rounded-full text-sm px-5 py-2.5 text-center mr-2 mb-2" on:click={todoAdd}>Add</button>
        <button id="emptybutton" class="text-white bg-red-600 hover:bg-red-700 focus:outline-none focus:ring-4 focus:ring-red-300 font-medium rounded-full text-sm px-5 py-2.5 text-center mr-2 mb-2" on:click={todoEmpty}>Empty</button>
    
    </form>
</div>