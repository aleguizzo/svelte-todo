<script>
    import { bind } from "svelte/internal";
    import "../../app.css";

    let todos = [];
    let bindtodo, bindtodo_check;
    function todoAdd() {
        todos.push({
            checked: false,
            text: bindtodo,
            style: "none",
        });
        todos = todos;
        bindtodo = "";
    }
    function todoRem(id) {
        let index = todos.indexOf(id);
        if (index !== -1) {
            todos.splice(index, 1);
            todos = todos;
        }
    }
    function todoEmpty() {
        todos = [];
        todos = todos;
    }
    $: {
        todos.forEach((todo) => {
            if (todo.checked) {
                todo.style = "line-through";
            } else {
                todo.style = "none";
            }
        });
        todos = todos
    };

</script>

<div class="p-5">
    <form id="inputform" onsubmit="preventDefault();" class="pt-5">
        <div class="flex flex-row">
            <input
                id="inputtodo"
                type="text"
                placeholder="Item text..."
                class="basis-2/3 bg-gray-50 border border-gray-300 text-gray-900 text-sm rounded-lg focus:ring-blue-500 focus:border-blue-500 mr-2 p-2.5"
                bind:value={bindtodo}
            />
            <button
                id="submitbutton"
                class="basis-1/6 text-white bg-red-600 hover:bg-red-700 focus:outline-none focus:ring-4 focus:ring-red-300 font-medium rounded-full text-sm px-5 py-2.5 text-center mr-2 my-auto "
                on:click={todoAdd}>Add</button
            >
            <button
                id="emptybutton"
                class="basis-1/6 text-white bg-red-600 hover:bg-red-700 focus:outline-none focus:ring-4 focus:ring-red-300 font-medium rounded-full text-sm px-5 py-2.5 text-center mr-2 my-auto "
                on:click={todoEmpty}>Empty</button
            >
        </div>
    </form>

    <ul>
        {#each todos as todo}
            <todo id={todo}>
                <div class="my-2 ">
                    <label for="">
                        <button
                            class="text-white bg-red-600 hover:bg-red-700 focus:outline-none focus:ring-4 focus:ring-red-300 font-medium rounded-full text-sm px-5 py-2.5 text-center"
                            on:click={todoRem(todo)}>X</button
                        >
                        <input
                            type="checkbox"
                            class="w-4 h-4 ml-2 inline-block text-blue-600 bg-gray-100 border-gray-300 rounded focus:ring-blue-500  focus:ring-2ml-3"
                            name=""
                            id=""
                            bind:checked={todo.checked}
                        />
                        <li class="mt-auto mb-auto inline-block ml-2 text-sm font-medium text-gray-900" style:text-decoration={todo.style}>{todo.text}</li>
                    </label>
                </div>
            </todo>
        {/each}
    </ul>
    
</div>
