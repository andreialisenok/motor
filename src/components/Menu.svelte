<script>
  import Button from "./Button.svelte";

export let data;
function test(event, item){
    item.expanded = event.detail;
    data = data;
}
</script>

<!-- <p on:click={toggleOpen}>
    {#if expanded}
    -
    {:else}
    +
    {/if}
    <span>{data['name']}</span>
</p> -->
<ul>
    {#each data as item}
    <li>
        <Button item={item} on:toggle={(e) => {test(e, item)}} />
        {#if item.expanded}
            {#if item.children }
                <ul>
                <li>
                    <svelte:self data={item.children}>
                        <Button item={item}/>
                    </svelte:self>
                </li>
                </ul>
            {/if}
        {/if}
    </li>
    {/each}
</ul>