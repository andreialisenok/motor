<script>
import Menu from './components/Menu.svelte';
import Search from './components/Search.svelte';

// import data from './data.json';

const data = [{
        "title": "Справочники",
        "children": [{
            "title": "Справочники1",
            "children": [{
                "title": "Справочники2"
            }]
        }]
    },
    {
        "title": "Контрагенты"
    },
    {
        "title": "Категории товаров"
    },
    {
        "title": "Товары",
        "children": [{
            "title": "Товары1"
        }, {
            "title": "Товары2"
        }, {
            "title": "Товары3",
            "children": [{
                "title": "Справочники33"
            }]
        }]
    }
]

let filteredData = data;







</script>

<div class="wrap">
    
    <Search filteredData={filteredData}/>
    <Menu data={data}/>
</div>


<style>
.wrap {
    display: flex;
    flex-direction: column;
    gap: 10px;
}
</style>
