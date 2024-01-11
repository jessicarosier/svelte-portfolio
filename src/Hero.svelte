<script>
    import {fade, blur, fly, slide, scale} from "svelte/transition";
    import {cubicIn, cubicOut} from "svelte/easing";

    let aboutMe = ["Full Stack Web Developer 👩🏽‍💻", "U.S Navy Veteran 🇺🇸⚓️", "Coffee Lover ☕️", "Traveler ✈️", "Lifelong Learner 📚", "Problem Solver 🧐", "Technology Enthusiast 💻"];

    let ms = 3000;
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


<div class="about-me-container d-flex flex-column flex-xl-row justify-content-center align-items-center">

  <div class="d-flex flex-column align-items-center">
    <div class="headshot-wrapper d-inline-block overflow-hidden object-fit-cover">
      <img class="w-100" src="img/headshot.jpg"
           alt="professional-headshot">
    </div>
  </div>

  <div class="d-flex flex-column align-items-center aboutMeText">
    <span> Hi <span class="wave">👋🏼</span>, I'm</span>
    <h3>Jessica Rosier</h3>
    {#if aboutMe}
      <p>
        {#key counter}
          {#if aboutMe[counter]}<span in:fade>{aboutMe[counter]}</span>{/if}
        {/key}
      </p>
    {/if}

    <div class="links-wrapper">
      <a class="button contact-button git" href="https://github.com/jessicarosier"
         target="_blank">
        <i class="devicon-github-original"></i>
      </a>
      <a class="button contact-button linkedin" href="https://www.linkedin.com/in/jessica-rosier/"
         target="_blank">
        <i class="devicon-linkedin-plain"></i>
      </a>
    </div>
  </div>


</div>


<style>

    .about-me-container {
        background-color: #f5f5f5;
        height: 100vh;
        font-family: var(--font);
        text-transform: uppercase;
        font-size: 2rem;
        font-weight: 600;
        color: #333;
        text-align: center;

        gap: 10px;

        @media (max-width: 768px) {

            gap: 20px;
        }
    }

    .aboutMeText {
        & h3 {
            font-size: 75px;
            font-weight: bold;
            margin: 0;

            @media (max-width: 768px) {
                font-size: 50px;
            }
        }

        & span {
            font-size: 50px;

            @media (max-width: 768px) {
                font-size: 30px;
            }
        }


        & p {
            width: 800px;

            @media (max-width: 768px) {
                width: 100%;
            }
        }
    }

    .headshot-wrapper {
        width: 275px;
        height: 275px;
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

    .links-wrapper {
        display: flex;
        justify-content: center;
        align-items: center;
        gap: 20px;
    }

    a.contact-button {
        display: flex;
        justify-content: center;
        align-items: center;
        position: relative;
        width: 50px;
        height: 50px;
        border-radius: 20px;
        background-color: var(--dark-purple);
        color: #fff;

        & img {
            border-radius: 20px;
            padding: 5px;
            width: 50px;
            height: 50px;

        }

    }

</style>