<script>
import Menu from './components/Menu.svelte';
import Search from './components/Search.svelte';

import data from './data.json';

let filteredData = data;


</script>

<div class="wrap">
    <Search data={filteredData}/>
    <Menu data={filteredData}/>
</div>

<style>
.wrap {
    display: flex;
    flex-direction: column;
    gap: 30px;
}
</style>
