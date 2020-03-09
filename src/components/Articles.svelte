<script>
    let listItems = fetch('https://node-hnapi.herokuapp.com/news?page=1').then(res => res.json());
</script>

<h2>Articles</h2>

<ul>
    {#await listItems}
       <p>Loading</p>
    {:then data}
      {#each data as item, i}
        <li>
            <a href="/detail/{item.id}">{item.title}</a><br>
        </li>
      {/each}
    {/await}
</ul>

