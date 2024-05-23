<script>
import Menu from './components/Menu.svelte';
import Search from './components/Search.svelte';
import data from './data.json';

let filteredData = data;



// $: visibleUsers = search ?
//     filteredData.filter(user => {
// 			return user.title.match(`${search}.*`) || user.title.match(`${search}.*`)
// 		}) : filteredData;
$: console.log(filteredData)

</script>

<div class="wrap">
    <Search bind:filteredData/>
    <Menu data={filteredData}/>
</div>

<style>
.wrap {
    display: flex;
    flex-direction: column;
    gap: 30px;
}
</style>
