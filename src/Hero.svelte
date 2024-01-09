<script>
    import {fade, blur, fly, slide} from "svelte/transition";
    import {tweened} from "svelte/motion";
    import {flip} from "svelte/animate";
    import {quintOut} from "svelte/easing";

    let aboutMe = ["Full Stack Web Developer 👩🏽‍💻", "U.S Navy Veteran 🇺🇸⚓️", "Coffee Lover ☕️", "Traveler ✈️", "Lifelong Learner 📚", "Problem Solver 🧐", "Technology Enthusiast 💻"];

    let ms = 1000;
    let counter = 0;
    const incr = () => {
        counter += 1;
        if (counter === aboutMe.length) {
            counter = 0;
        }
    };

    let clear;
    $: {
        clearInterval(clear);
        clear = setInterval(incr, ms);
    }
</script>


<div class="about-me-container d-flex flex-row flex-xl-column justify-content-center align-items-center">
  <div class="d-flex flex-column align-items-center">
    <span> Hi <span class="wave">👋🏼</span>, I'm</span>
    Jessica Rosier
    {#if aboutMe}
      <p class="aboutMe__container__text__p">
        {#if aboutMe[counter]}<span>{aboutMe[counter]}</span>{/if}
      </p>
    {/if  }
  </div>

  <div class="d-flex flex-column align-items-center">
    <div class="headshot-wrapper d-inline-block position-relative overflow-hidden object-fit-cover">
      <img class="w-100" src="img/headshot.jpg"
           alt="professional-headshot">
    </div>
  </div>

</div>


<style>

    .about-me-container {
        height: 100vh;
        width: 100%;
        background-color: #f5f5f5;
        font-family: var(--font);
        text-transform: uppercase;
        font-size: 2rem;
        font-weight: 600;
        color: #333;
        text-align: center;
        padding: 0 1rem;
    }

    .headshot-wrapper {
        width: 250px;
        height: 250px;
        border-radius: 50%;
    }

    .headshot-wrapper img {
        height: auto;
        margin-top: -55px;

        &:hover {
            cursor: pointer;
            height: auto;
            margin-top: -55px;
        }


    }

</style>