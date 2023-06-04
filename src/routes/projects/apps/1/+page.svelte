<script>
    import Icon from "../../../../components/Icon.svelte";

    let newItem = '';
    let todoList =[];
    function add() {
        if(newItem !== ''){
            todoList = [
                ...todoList,
                {
                   Task: newItem,
                   Complited: false, 
                }
            ]
            newItem = '';
        }
    }

    function complite(index) {
        todoList[index].Complited = !todoList[index].Complited
    }

    function remove(index) {
        todoList.splice(index, 1)
        todoList = todoList;
    }
</script>

<main>
    <form on:submit|preventDefault={add}>
        <input bind:value={newItem} placeholder="Enter todo" />
        <button class="add-todo" on:click={add}><span>+</span> </button>
    </form>
    <div class="todos">
        {#each todoList as item, index}
        <div class="todo" class:complited={item.complited}></div>
            <span class="todo_text">{item.Task}</span>
            <div class="todo-buttons">
                <button class="todo-button" on:click={() => complite(index)}>
                    <Icon name="check-mark" />
                </button>
                <button class="todo-button" on:click={() => remove(index)}>
                    <Icon name="delete" />
                </button>
            </div>
        {/each}
    </div>
</main>

<style>
    main {
        display: flex;
        flex-direction: column;
        align-items: center;
        min-height: 100%;
        padding: 5vmin;
        box-sizing: border-box;
        background: rgb(150, 8, 8);
        border-radius: 10px;
    }
    form {
        width:100%;
        max-width: 500px;
        display: flex;
        align-items: center;
        margin-bottom: 1rem;
        
    }

    input {
        flex-grow: 1;
        width: 0;
        border:none;
        border-bottom: 1px solid black;
        box-shadow: none;
        font-size: 1.2rem;
        outline: none;
        border-radius: 5px;
    }
    
    .todos {
        width: 100%;
        max-width: 500px;

    }

    .todo_text {
        display: flex;
        padding: 20px;
        border-radius: 20px;
        box-shadow: 0 0 15px black;
        background-color: hsla(0, 0% , 100% , 0.2);
        margin-top: 1rem;
        font-size:  1.2rem;
        color: white;
        justify-content: space-between;
        align-items: center;
    }
    
    .add-todo {
        border: 1px solid black;
        border-radius: 5px 5px 0px 0px;
        margin-left: 2px;
        background-color: white;
        color: black;
    }
    
    .todo-buttons {
        display: flex;
        align-items: center;
        margin-left: 1rem;
    }

    .todo-button {
        flex-shrink:0;
        width: 32px;
        height: 32px;
        padding: 4px;
        margin: 0;

    }
</style>
