<script>
    import { bind } from "svelte/internal";
    import "../../app.css";


    let todos = []
    let bindtodo, bindtodo_check
    function todoAdd(){
        todos.push({
            checked: false,
            text: bindtodo,
        })
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
    <form id="inputform" onsubmit="preventDefault();" class="pt-5">
        <input id="inputtodo" type="text" placeholder="Item text..." class="bg-gray-50 border border-gray-300 text-gray-900 text-sm rounded-lg focus:ring-blue-500 focus:border-blue-500  p-2.5" bind:value={bindtodo}>
        <button id="submitbutton" class="text-white bg-red-600 hover:bg-red-700 focus:outline-none focus:ring-4 focus:ring-red-300 font-medium rounded-full text-sm px-5 py-2.5 text-center mr-2 mb-2" on:click={todoAdd}>Add</button>
        <button id="emptybutton" class="text-white bg-red-600 hover:bg-red-700 focus:outline-none focus:ring-4 focus:ring-red-300 font-medium rounded-full text-sm px-5 py-2.5 text-center mr-2 mb-2" on:click={todoEmpty}>Empty</button>
    
    </form>
    
    <ul>
        <!-- Todos here-->
        {#each todos as todo}
            <todo id={todo}>
                <div>
                    <button class="text-white bg-red-600 hover:bg-red-700 focus:outline-none focus:ring-4 focus:ring-red-300 font-medium rounded-full text-sm px-5 py-2.5 text-center mr-2 mb-2" on:click={todoRem(todo)}>X</button>
                    <input type="checkbox" class="w-4 h-4 text-blue-600 bg-gray-100 border-gray-300 rounded focus:ring-blue-500  focus:ring-2" name="" id="" bind:checked={todo.checked}>
                    <li class="inline-block">{todo.text}</li>
                </div>
                
            </todo>
        {/each}
    </ul>
    
</div>