<script>
    import { params } from '@sveltech/routify'
    import Comment from '../../components/Comment.svelte'

    export let postId;

    let detail = fetch('https://node-hnapi.herokuapp.com/item/'+postId).then(res => res.json());
</script>

{#await detail}
   <p>Loading</p>
{:then data}

    <h1><a href="{data.url}">{data.title}</a></h1>
    <p>Submitted by {data.user} - {data.time_ago}</p>

    <ul>
        <Comment comment={data} />
    </ul>

{/await}
