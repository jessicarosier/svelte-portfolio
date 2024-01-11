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

    function openMenu() {
        const menu = document.querySelector(".side-menu");
        menu.style.right = "0";
    }

    function closeMenu() {
        const menu = document.querySelector(".side-menu");
        menu.style.right = "-300px";

    }

</script>

<nav>
  <ul class="side-menu">
    {#each navLinks as link}
      <li>
        <a href="{link.link}">{link.name}</a>
      </li>
    {/each}
    <span on:click={() => closeMenu()} on:keypress={() => closeMenu()} class="material-icons menu-icons close-menu">
close
</span>
  </ul>
  <span on:click={() => openMenu()} on:keypress={() => openMenu()} class="material-icons menu-icons open-menu">
menu
</span>
</nav>

<style>

    nav {
        position: fixed;
        width: 100%;
        display: flex;
        align-items: center;
        justify-content: center;
        flex-wrap: wrap;
        background-color: var(--dark-purple);
        padding: 0;
        margin: 0;
        font-family: var(--font);
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
        font-size: 20px;
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

    nav .menu-icons {
        display: none;
    }

    @media only screen and (max-width: 768px) {
        nav {
            justify-content: end;
        }

        nav .menu-icons {
            display: block;
            cursor: pointer;
            margin-right: 30px;
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

        nav ul .menu-icons {
            position: absolute;
            top: 25px;
            left: 25px;
            cursor: pointer;
        }
    }


</style>