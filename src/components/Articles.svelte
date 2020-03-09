<script>
    let listItems = fetch('https://node-hnapi.herokuapp.com/news?page=1').then(res => res.json());
</script>
    
<style>

    h2 {
        font-size: 2.4rem;
    }
    
    li {
        border-bottom: 1px solid #DDD;
    }
    
    a {
        text-decoration: none;
        padding: 1.6rem;
        display: block;
    }

    a:hover {
        background: #EEE;
    }
</style>

<ul>
    {#await listItems}
       <p>Loading</p>
    {:then data}
      {#each data as item, i}
        <li>
            <a href="/detail/{item.id}">{item.title}</a>
        </li>
      {/each}
    {/await}
</ul>
