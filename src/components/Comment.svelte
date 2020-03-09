<script>
  export let comment;
</script>

{#each comment.comments as comment}
  <li class="c-comment">
    <p class="c-comment__user">{comment.user} {comment.time_ago}</p>
    <div class="c-comment__text">
      {@html comment.content}
    </div>
    <svelte:self {comment} />
  </li>
{/each}
