<script>
export let filteredData;

// @ts-ignore
function getSearch(arr, name) {
  for (let child of arr) {
    const title = child.title.toLowerCase();
    if (title.includes(name.toLowerCase())) {
    console.log(child);
      return child;
    // console.log(title);
    } else if (child.children && child.children.length > 0) {
      var x = getSearch(child.children, name);

      // @ts-ignore
      if (x){
        console.log(child);
        return Array.isArray(x) ? [child, ...x] : [child, x];
        // console.log(Array.isArray(x) ? [child.title, ...x] : [child.title, x]);
      }
    }
  }
}

function test(arr, name) {
    let searchData = getSearch(arr, name);
}

let searchValue = ""




import { createEventDispatcher } from 'svelte';
const dispatch = createEventDispatcher();

function changeText() {
		dispatch('message', {
			text: 'Hello!'
		});
	}

let txt = ''
</script>
<input type="text" on:change={changeText} bind:value={txt}>
<h1>{txt}</h1>
<input type="text" bind:value={searchValue} on:input={() => {test(filteredData, searchValue)}}>
