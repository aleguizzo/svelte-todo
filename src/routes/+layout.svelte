<style>
    nav {
        padding: 1rem;
        background-color: darkgray;
        display: flex;
    }
    nav a {
        color: #fff;
        text-decoration: none;
        padding-left: 10px;
        margin-top: auto;
        margin-bottom: auto;
        font-family: system-ui, -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Oxygen, Ubuntu, Cantarell, 'Open Sans', 'Helvetica Neue', sans-serif;
    }
    nav img{
        height: 30px;
    }
</style>
<!-- create simple nav bar-->
<nav>
    <img src="https://www.alegsoftware.ga/immagini/logo_small.png" alt="..."/>
    <a href="/">Home</a>
    <a href="/about">About</a>
    <a href="/todo">To-do Test</a>
</nav>


<slot>

</slot>