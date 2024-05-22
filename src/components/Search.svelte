<script>
  export let data;

  // @ts-ignore
  function getSearch(arr, name) {
    for (let child of arr) {
      const title = child.title.toLowerCase();
      if (title.includes(name.toLowerCase())) {
      console.log(child);
      console.log(name);
      console.log('111');

        return name;
      // console.log(title);
      } else if (child.children && child.children.length > 0) {
        var x = getSearch(child.children, name);
  
        // @ts-ignore
        if (x){
          console.log('22');
          return Array.isArray(x) ? [child, ...x] : [child, x];
          // console.log(Array.isArray(x) ? [child.title, ...x] : [child.title, x]);
        }
      }
    }
  }
//   function getSearch(arr, name) {
//   for (let child of arr) {
//     console.log(child.children);
//     const title = child.title.toLowerCase();
//     if (title.includes(name.toLowerCase())) {
//       return name;
//     } else if (child.children.length > 0) {
//       var x = getSearch(child.children, name);

//       if (x) return Array.isArray(x) ? [child.name, ...x] : [child.name, x];
//     }
//   }
// }

  let searchValue = ""
  
  </script>
  <input type="text" bind:value={searchValue} on:input={() => {getSearch(data, searchValue)}}>