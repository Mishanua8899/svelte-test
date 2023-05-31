<script>
    const nav = [
        {
            title: "About me",
            href: "/about",
            isShow: true,
        },

        {
            title: "Blog",
            href: "/blog",
            isShow :true
        },

        {
            title: "My projects",
            href: "/myPrgct",
            isShow :true
        },

        {
            title: "Contacts",
            href: "/contacts",  
            isShow:false,
        },
    ];
</script>

<nav>
    <div class="nav-conitainer">
        <a href="/" class="nav-log" title="Back To Homepage">Misha</a>
        <div class="nav-links">
           {#each nav as link}
               {#if link.isShow}
                    <a href={link.href} class="link">{link.title}</a>
               {/if}
           {/each}
        </div>
    </div>
</nav>
<div class="container">
    <slot></slot>
</div>

<style>
   /* .container {
        display: flex;
        min-width: 1400px;
        margin: 50px auto;
        
    }*/
</style>
