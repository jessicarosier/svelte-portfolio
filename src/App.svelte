<script>
    import Nav from "./Nav.svelte";
    import Hero from "./Hero.svelte";
    import Projects from "./Projects.svelte";
    import Certifications from "./Certifications.svelte";
    import Skills from "./Skills.svelte";


</script>

<main class="page-wrapper">
  <div class="hero-wrapper">
    <Nav/>

    <Hero/>

  </div>


    <Projects />

    <Certifications />

  <Skills />





</main>

<style>


    @media (min-width: 640px) {
        main {
            max-width: none;
        }
    }
</style>