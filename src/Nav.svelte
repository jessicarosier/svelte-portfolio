<script>
    const navLinks = [
        {
            name: "< Home >",
            link: "index.html"
        },
        {
            name: "< About >",
            link: "about.html"
        },
        {
            name: "< Projects >",
            link: "projects.html"
        },
        {
            name: "< Skills >",
            link: "skills.html"
        },
        {
            name: "< Contact >",
            link: "contact.html"
        },

    ];

</script>

<nav>
  <ul>
    {#each navLinks as link}
      <li>
        <a href="{link.link}">{link.name}</a>
      </li>
    {/each}
  </ul>
</nav>

<style>

    nav {
        display: flex;
        align-items: center;
        justify-content: center;
        flex-wrap: wrap;
        background-color: var(--dark-purple);
        padding: 0;
        margin: 0;
        font-family: var(--font);
        font-size: 20px;
        font-weight: bolder;
        text-transform: uppercase;
        letter-spacing: 5px;
        min-height: 10vh;
    }


    nav ul li {
        display: inline-block;
        list-style: none;
        margin: 10px 20px;
    }

    nav ul li a {
        color: white;
        text-decoration: none;
        font-size: 18px;
        position: relative;
    }

    nav ul li a::after {
        content: '';
        width: 0;
        height: 3px;
        background-color: white;
        position: absolute;
        left: 0;
        bottom: -6px;
        transition: 0.5s;

    }

    nav ul li a:hover::after {
        width: 100%;
    }


</style>