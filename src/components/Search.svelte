<script>
export let filteredData;
// $: console.log(filteredData);
// @ts-ignore
const getSearch = () => {	
		return filteredData.filter(item => {
			let itemTitle = item.title.toLowerCase();
			return itemTitle.includes(searchValue.toLowerCase())
		});
	}

  function getSearch1(arr, name) {
  for (let child of arr) {    
    const title = child.title.toLowerCase();

    if (title.includes(name.toLowerCase())) {
      console.log(child);
      return child;
    } else if (child.children && child.children.length > 0) {
      var x = getSearch1(child.children, name);

      if (x) {
        console.log(Array.isArray(x) ? [child.title, ...x] : [child.title, x]);
        return Array.isArray(x) ? [child.title, ...x] : [child.title, x];
      };
    }
  }
}


let searchValue = ""
</script>

<!-- <input type="text" bind:value={searchValue} on:input={() => {getSearch1(filteredData, searchValue)}}> -->
<input type="text" bind:value={searchValue} on:input={getSearch}>

