<script>
    import { routes } from "./routes.js";
</script>

<svelte:head>
    <title>My Projects</title>
</svelte:head>

<div class="container">
    <h1>My projects</h1>
    <div class="apps">
        {#each routes as page}
        <div class="app">
            <h2>{page.title}</h2>
            <p>{page.body}</p>
            <p class="readmore">
                <a href="/projects/{page.id}" class="link">Read more</a>
            </p>
        </div>
        {/each}
    </div>
</div>
