<script>
import Menu from './components/Menu.svelte';
import data from './data.json';

let filteredData = data;

let searchValue = ""

const getSearch = (data, string) => filteredData = data.flatMap(o => {
        if (o.title.toLowerCase().includes(string)) return o;
        const children = getSearch(o.children || [], string);
        if (children.length) return { ...o, children };
        return filteredData;
    })
// filteredData = filter(data, '22');
// const a = getSearch(data, '22')
$: console.log(filteredData);
</script>

<div class="wrap">
    <input bind:value={searchValue} on:input={() => getSearch(data, searchValue)} />
    {#if filteredData.length > 0}
        <Menu data={filteredData} />
    {:else}
        <p>not found</p>
    {/if}
</div>

<style>
.wrap {
    display: flex;
    flex-direction: column;
    gap: 30px;
}
</style>
