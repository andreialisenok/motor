<script>
    import Button from "./Button.svelte";
  
  export let data;

  
  function test(event, item){
      item.expanded = event.detail;
      data = data;
  }
  </script>

<ul>
    {#each data as item}
    <li>
        <Button item={item} on:toggle={(e) => {test(e, item)}} />
        {#if item.expanded}
            {#if item.children }
                <ul>
                <li>
                    <svelte:self data={item.children}>
                        <Button item={item} />
                    </svelte:self>
                </li>
                </ul>
            {/if}
        {/if}
    </li>
    {/each}
</ul>

<style>

    ul {
        margin: 0;
    padding: 0;
    list-style: none;
    width: 100%;
    display: flex;
    flex-direction: column;
    gap: 1px;
    }  
   
    
</style>