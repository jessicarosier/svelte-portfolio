<script>
    const navLinks = [
        {
            name: "< Home >",
            link: "#top"
        },
        {
            name: "< About >",
            link: "#about"
        },
        {
            name: "< Projects >",
            link: "#projects"
        },
        {
            name: "< Skills >",
            link: "#skills"
        },
        {
            name: "< Contact >",
            link: "#contact"
        },

    ];

</script>

<nav>
  <ul >
    {#each navLinks as link}
      <li>
        <a href="{link.link}">{link.name}</a>
      </li>
    {/each}
  </ul>
  <p>© 2024 by Jessica Rosier. This site was built using Svelte. <i class="devicon-svelte-plain colored"></i></p>
  <p>See the source code here: <a href="https://github.com/jessicarosier/svelte-portfolio" target="_blank"><i class="devicon-github-original colored"></i></a></p>
</nav>

<style>

    nav {
        display: flex;
        flex-direction: column;
        align-items: center;
        justify-content: center;
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

    p {
        margin-top: 20px;
        font-weight: bolder;
        text-transform: capitalize;
    }

    @media only screen and (max-width: 768px) {
        nav {
            justify-content: end;
        }


        nav ul {
            background: var(--dark-purple);
            position: fixed;
            top: 0;
            right: -300px;
            width: 300px;
            height: 100vh;
            padding-top: 50px;
            z-index: 2;
            transition: right 0.5s;
        }

        nav ul li {
            display: block;
            margin: 25px;
        }

    }


</style>