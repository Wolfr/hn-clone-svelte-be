<script>
    let listItems = fetch('https://node-hnapi.herokuapp.com/news?page=1').then(res => res.json());
</script>
    
<style>

    h2 {
        font-size: 2.4rem;
    }
    
    li {
        border-bottom: 1px solid #DDD;
        padding: 1.6rem;
    }
    
    span {
        font-size: 90%;
        color: #666;
    }
    
    a {
        text-decoration: none;
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
            <a href="/detail/{item.id}">
                {item.title} <span>({item.domain})</span>
            </a>
            <ul>
                <li>{item.points} points by {item.user}</li>
                <li>{item.comments_count} comments</li>
            </ul>
        </li>
      {/each}
    {/await}
</ul>
