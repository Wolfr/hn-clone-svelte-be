<script>
  export let comment;
</script>
  
<style>

    .c-comment {
        margin: 2rem;
    }
    
    .c-comment li {
        padding-left: 2.4rem;
    }
    
    .c-comment__user {
        color: #666;
    }

    .c-comment__user span {
        font-weight: 600;
        color: #000;
    }
    


</style>

{#each comment.comments as comment}
  <li class="c-comment">
    <p class="c-comment__user"><span>{comment.user}</span> {comment.time_ago}</p>
    <div class="c-comment__text">
      {@html comment.content}
    </div>
    <svelte:self {comment} />
  </li>
{/each}
