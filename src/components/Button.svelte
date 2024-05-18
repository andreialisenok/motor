<script>
export let item;
import { createEventDispatcher } from "svelte";
const dispatch = createEventDispatcher();

let expanded = false;
function toggleOpen() {
    expanded = !expanded;
    dispatch("toggle", expanded);
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
<button on:click={toggleOpen}>
    {item.title}
</button>
