<script>
    export let item;
    import { createEventDispatcher } from "svelte";
    const dispatch = createEventDispatcher();
    
    export let expanded = false;
    function toggleOpen() {
        expanded = !expanded;
        dispatch("toggle", expanded);
    }
    </script>
    <button on:click={toggleOpen}>
        {item.title}
    </button>
    <style>
        button {
           width: 100%;
       }
   </style>