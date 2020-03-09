<script>
    import { params } from '@sveltech/routify'
    import Comment from '../../components/Comment.svelte'

    export let postId;

    let detail = fetch('https://node-hnapi.herokuapp.com/item/'+postId).then(res => res.json());
</script>
    
<style>
    
    .detail-header {
        padding: 1.6rem;
    }

</style>

<svelte:head>
    <title>{#await detail}Loading...{:then data}{data.title}{/await}</title>
</svelte:head>

{#await detail}
   <p>Loading</p>
{:then data}

    <div class="detail-header">
        <h1><a href="{data.url}">{data.title}</a></h1>
        <p>Submitted by {data.user} - {data.time_ago}</p>
    </div>
    
    <main>
        <ul>
            <Comment comment={data} />
        </ul>
    </main>

{/await}
