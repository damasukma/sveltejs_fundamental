<script>
    export let url;

    
    const fetchData= async () => {
    try
      {
        console.log(url)  
        const res = await fetch(url)
        const json = await res.json()
        console.log(json)
        return json
       }
        catch(err)
        {
            return {status: 500, data: []}
        }

      

    }

    let getData = fetchData()




</script>

<main>
   {#await getData}
     <p>...Waiting</p>
   {:then  data}
        {#each data as row (row.id)}
        <p>UserId #{row.userId}</p>
        <p>Title #{ row.title }</p>
        {/each}
   {:catch error}
     <p>Error {error}</p>
   {/await}
</main>