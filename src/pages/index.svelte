<script>
    import Articles from '../components/Articles.svelte';
</script>

<style>

    main h2 {
        padding: 1.6rem;
        font-weight: 600;
        color: #000;
    }

</style>

<svelte:head>
    <title>Hacker News</title>
</svelte:head>

<main>
    <h2 class="c-h2">Articles</h2>
    <Articles />
</main>
