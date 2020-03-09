<style>
    
    ul {
        display: flex;
        margin: 0.4rem 0;
        font-size: 1.3rem;
    }

    li {
        padding-right: 1rem;
        margin-right: 1rem;
        border-right: 1px solid #CCC;
    }
    
    li:last-child {
        border: none;
    }

</style>

<script>
    export let item;
</script>

<ul>
    <li>{item.points} points by {item.user}</li>
    <li>{item.comments_count} comments</li>
</ul>