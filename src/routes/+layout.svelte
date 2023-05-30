<script>
    const nav = [
        {
            title: "About me",
            href: "/about",
        },

        {
            title: "Blog",
            href: "/blog",
        },

        {
            title: "My projects",
            href: "/myPrgct",
        },

        {
            title: "Contacts",
            href: "/contacts"  
        },
    ];
</script>

<nav>
    <div class="nav-conitainer">
        <a href="/" class="nav-log" title="Back To Homepage">Misha</a>
        <div class="nav-links">
           {#each nav as link}
               <a href={link.href} class="link">{link.title}</a>
           {/each}
        </div>
    </div>
</nav>
<div class="container">
    <slot></slot>
</div>

<style>
    .container {
        display: flex;
        min-width: 1400px;
        margin: 50px auto;
    }
</style>
