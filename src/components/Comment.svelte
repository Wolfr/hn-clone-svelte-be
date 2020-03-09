<script>
  export let comment;
</script>
  
<style>

    .c-comment {
        margin: 2rem;
        padding-left: 2.4rem;
    }
    
    .c-comment__user {
        font-weight: 600;
    }
    


</style>

{#each comment.comments as comment}
  <li class="c-comment">
    <p class="c-comment__user">{comment.user} {comment.time_ago}</p>
    <div class="c-comment__text">
      {@html comment.content}
    </div>
    <svelte:self {comment} />
  </li>
{/each}
