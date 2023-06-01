<svelte:head>
  <title>About me</title>
</svelte:head>

<div class="container">
    <h1> About Me</h1>
        <div class="blogposts">
            {#each routes as page}
             <div class="post">
                <h2>{page.title}</h2>
                <p>{page.body}</p>
             <div class="readmore">
                <a href="/about/post/{page.id}" class="link">Read more</a>
             </div>
            </div>
            {/each}
        </div>
</div>





<script>
    import {routes} from "./routes.js";
</script>

<style>
    .container {
        margin: 50px auto;
        min-width: 800px;
        padding: 0 20px;
    }

    .blogposts {
        display: grid;
        grid-template-columns: 1fr 1fr;
        grid-gap: 20px;
        
    }
    .post{ 
        border: 1px solid #dddd;
        padding: 10px;
        box-shadow: 0 0 10px #eee;
    }
    .link {
        color: rgb(10, 10, 139);
        overflow: auto;
    }
</style>