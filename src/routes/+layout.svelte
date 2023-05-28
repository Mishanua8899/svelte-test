<nav>
    <div class="nav-conitainer">
        <a href="/" class="nav-log" title="Back To Homepage">Misha</a>
        <div class="nav-links">
            <a href="/about" class="link">About Me</a>
            <a href="/about" class="link">Blog</a> 
            <a href="/about" class="link">My Projects</a>
            <a href="/about" class="link">Contacts</a>
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
        margin: 50px auto
        ;
    }

</style>