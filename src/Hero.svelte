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


<div class="about-me-container d-flex flex-column flex-xl-row justify-content-center align-items-center gap-5">
  <div class="d-flex flex-column align-items-center aboutMeText">
    <span> Hi <span class="wave">👋🏼</span>, I'm</span>
    Jessica Rosier
    {#if aboutMe}
      <p>
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
        background-color: #f5f5f5;
        font-family: var(--font);
        text-transform: uppercase;
        font-size: 2rem;
        font-weight: 600;
        color: #333;
        text-align: center;
    }

    .aboutMeText {
        font-size: 50px;

        & p {
            width: 800px;

            @media (max-width: 768px) {
                width: 100%;
            }
        }
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