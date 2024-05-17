<script>
// import Menu from './components/Menu.svelte';
// import Search from './components/Search.svelte';

// import data from './data.json';

const data = [{
        "title": "Справочники",
        "children": {
            "title": "Справочники1",
            "children": {
                "title": "Справочники2"
            }
        }
    },
    {
        "title": "Контрагенты"
    },
    {
        "title": "Категории товаров"
    },
    {
        "title": "Товары",
        "children": {
            "title": "Товары1"
        }
    }
]
let filteredItems = [];

// const handleInput = () => {
// return filteredItems = data.filter(item => item.toLowerCase().match(inputValue.toLowerCase()));
// }
// subName: [{

//         name: 'Контрагенты'
//     }, {
//         name: 'Категории товаров'
//     }, {
//         name: 'Товары'
//     }, {
//         name: 'Регионы'
//     }, {
//         name: 'Брак'
//     }, {
//         name: 'Зоны'
//     }, {
//         name: 'Тары'
//     }, {
//         name: 'Тележки'
//     }, {
//         name: 'Типы упаковки'
//     }, {
//         name: 'Причина замены ячейки'
//     }, {
//         name: 'Причины отмены процесса перемещения '
//     }, {
//         name: 'Типы исключительной ситуаций'
//     }, {
//         name: 'Типы брака'
//     },

// ]
</script>

<div class="wrap">

    <ul>
        {#each data as item}
        <li>
            <button> {item.title}</button>
            {#if item.children}
            <span>{console.log(item.children)}</span>
            <ul>
                {#each data as item}
                <li>
                    <button>{item.title}</button>
                </li>
                {/each}
            </ul>
            {/if}
        </li>
        {/each}
    </ul>

</div>

<style>
.wrap {
    display: flex;
    flex-direction: column;
    gap: 10px;
}
</style>
