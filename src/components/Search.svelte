<script>
  export let filteredData;
  
  // @ts-ignore
  function getSearch(arr, name) {
    
    // for (let child of arr) {
    //   const title = child.title.toLowerCase();
    //   if (title.includes(name.toLowerCase())) {
    //   console.log(child);
    //     return child;
    //   // console.log(title);
    //   } else if (child.children && child.children.length > 0) {
    //     var x = getSearch(child.children, name);
    //     // @ts-ignore
    //     if (x){
    //       console.log(child);
    //       return Array.isArray(x) ? [child, ...x] : [child, x];
    //       // console.log(Array.isArray(x) ? [child.title, ...x] : [child.title, x]);
    //     }
    //   }
    // }
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
  <input type="text" bind:value={searchValue} on:input={() => {getSearch1(filteredData, searchValue)}}>