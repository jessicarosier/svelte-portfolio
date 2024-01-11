<script>


</script>

<footer>
  <p>© 2024 by Jessica Rosier. This site was built using Svelte. <i class="devicon-svelte-plain colored"></i></p>
  <p>See the source code <a href="https://github.com/jessicarosier/svelte-portfolio" target="_blank"> <span>here</span><i class="devicon-github-original colored"></i></a></p>
</footer>

<style>

    footer {
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
        color: white;
    }



    p {
        margin-top: 20px;
        font-weight: bolder;
        text-transform: capitalize;
        padding: 0 20px;

        & a span {
            color: cornflowerblue;
            font-weight: bolder;

        }
    }

    @media only screen and (max-width: 768px) {
        nav {
            justify-content: end;
        }


    }


</style>