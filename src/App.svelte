<script>
    import Nav from "./Nav.svelte";
    import Hero from "./Hero.svelte";
    import Projects from "./Projects.svelte";
    import Certifications from "./Certifications.svelte";
    import Skills from "./Skills.svelte";
    import Contact from "./Contact.svelte";
    import Footer from "./Footer.svelte";
    import AboutMe from "./AboutMe.svelte";

    //boolean to check if element is in view
    let isProjectsActive = false;
    let isAboutMeActive = false;

    //scroll position
    let y;

    // window.onscroll = function () {
    //     console.log(window.pageYOffset);
    // };

    //if the scroll position is greater than 400px, then the element is in view
    $: if (y > 400 && y < 2000) {
        isProjectsActive = true;
    } else {
        isProjectsActive = false;
    }

    $: if (y > 1425 && y < 2480) {
        isAboutMeActive = true;
    } else {
        isAboutMeActive = false;
    }

    let konamiCode = "ArrowUpArrowUpArrowDownArrowDownArrowLeftArrowRightArrowLeftArrowRightbaEnter";
    let secretCode = "";
    window.addEventListener("keyup", (e) => {
        e.preventDefault();
        let code = e.key;
        secretCode += code;
        if (secretCode.includes(konamiCode)) {
           alert("You have unlocked the secret code!");
        }
    });

</script>

<!--binds the scroll position to the y variable so we always have the current scroll position -->
<svelte:window bind:scrollY={y}/>

<main class="page-wrapper">
  <div class="hero-wrapper">
    <Nav/>
    <Hero/>
  </div>

  <div class:hidden={!isProjectsActive} class="transitionElement">
    <Projects/>
  </div>

  <div class:hidden={!isAboutMeActive} class="transitionElement">
    <AboutMe/>
  </div>

  <Certifications/>

  <Skills/>

  <Contact/>

  <Footer/>

</main>
