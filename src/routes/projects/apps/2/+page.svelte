<script>
    let sum = '';
    let name = '';

    let Storage_of_List = [];

    function add() {
        if((sum !== '' && name !== '') && (typeof((+sum)) === 'number')){
            Storage_of_List = [
                ...Storage_of_List,
                {
                    Name: name,
                    Summa: sum,
                    Visiable: true,
                }
            ]
            sum = '';
            name = '';
        }
    }

    function remove(index){
        Storage_of_List.splice(index, 1)
        Storage_of_List = Storage_of_List

    /*    Storage_of_List[index].Visiable = !Storage_of_List[index].Visiable*/
    }
</script>

<main>
    <div class="container">
        <h1>Учет расходов</h1>
        <form class="form">
            <label for="name">
                <input type="text" class="name_of_action" placeholder="Введите название" bind:value={name}/>
            </label>
            <label for="sum">
                <input type="text" class="summa" placeholder="Введите сумму" bind:value={sum}/>
            </label>
            <button class="input_data" on:click={add}>Добавить</button>
        </form>
        <table class="storage">
            <caption>&dArr;</caption>
            <tr>
                <th class="header">Названия</th>
                <th class="header">Сумма</th>
                <th class="header">Действия</th>
            </tr>
            {#each Storage_of_List as item, index}
            {#if item.Visiable}
            <tr>
                <th>{item.Name}</th>
                <th>{item.Summa}</th>
                <th><button on:click={remove(index)}>Удалить</button></th>
            </tr>
            {/if}
            {/each}
            
        </table>
    </div>
</main>

<style>
    .storage {
        border-collapse: collapse ;
    }
    tr,th {
        border: 1px solid;
        padding: 5px 15px 5px 15px;
    }
    main {
        display: flex;
        flex-direction: column;
        margin-left: 20px;
        font-family: system-ui, -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Oxygen, Ubuntu, Cantarell, 'Open Sans', 'Helvetica Neue', sans-serif;
        width: 100%;
        height: 100%;
        align-items: center;
        text-align: center;
    }
    .form {
        display: grid;
        grid-template-rows: 50px 50px;
    }

    .input_data {
        width: fit-content;
        border: 1qpx solid black;
        background-color: rgb(0, 204, 0);
        padding: 5px;
        border-radius: 5px;
        transition: all 0.3s ease;
        color: white;
    }

    .input_data:hover {
        background-color: rgb(0, 255, 0);
        transition: all 0.3s ease;
    }

    .header {
        background-color: rgb(180, 180, 180);
    }
</style>