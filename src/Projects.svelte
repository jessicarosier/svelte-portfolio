<script>
    import {fade, blur, fly, slide, scale, crossfade} from "svelte/transition";
    import {tweened} from "svelte/motion";
    import {flip} from "svelte/animate"; //must be used in for each block
    import {
        quintOut,
        backInOut,
        backOut,
        backIn,
        cubicOut,
        cubicIn,
        cubicInOut,
        sineInOut,
        expoInOut,
        bounceInOut,
        linear
    } from "svelte/easing";
    import {transition_in} from "svelte/internal";

    export let activeIndex = 0;
    const projects = [
        {
            name: "Favorite Movies App",
            description: "This web app allows users to search for movies and add them to a list of favorites. The app uses the TMDB API to search for movies and retrieve movie data as well as a local JSON database to store the list of favorite movies. Technologies used include HTML, CSS, JavaScript, bootstrap, and JSON server.",
            img: "img/preview/movies-mbp.jpeg",
            alt: "screenshot of movies app",
            github: "https://github.com/jessicarosier/favorite-movies-app",
            liveSite: "https://movies-app.jessicarosier.com"
        },
        {
            name: "Weather Map",
            description: "This is a weather app created using HTML, CSS, and JavaScript. The app uses the OpenWeatherMap API to retrieve weather data for a given location as well as the MapBox API to display a map of the location.",
            img: "img/preview/weather-mbp.jpeg",
            alt: "screenshot of weather app",
            github: "https://github.com/jessicarosier/weather-map",
            liveSite: "https://weather-map.jessicarosier.com/"
        },
        {
            name: "Coffee Project",
            description: "This is a simple website demonstrating the use of HTML, CSS,and DOM manipulation with JavaScript. The website is a single page that displays information about coffee. Users can search for coffee by name, or roast type and add new coffee to the page. Local storage is used to make the newly added coffee persist on the page.",
            img: "img/preview/coffee-mbp.jpeg",
            alt: "screenshot of coffee project",
            github: "https://github.com/jessica-nani-coffee-project/coffee-project/tree/main",
            liveSite: "https://coffee.jessicarosier.com"
        },

        {
            name: "Ducklister",
            description: "Ducklister is a full stack web application that allows a niche community of jeep enthusiasts to share their love for rubber ducks. Users can register for a new account, edit their profile, list ducks they want to share, and engage with fellow duck lovers. Technologies used include HTML, CSS, JavaScript, Java, and MySQL. Ducklister was mapped using servlets, and JSPs were used to generate HTML pages. Prepared statements were used to prevent SQL injection, and BCrypt algorithm was used to hash passwords.",
            img: "img/preview/ducklister-mbp.jpeg",
            alt: "screenshot of ducklister",
            github: "https://github.com/Genesis-Luis-Jessica-Adlister/ducklister",
        },

        {
            name: "Map-Share",
            description: "Map-Share is a full stack web application that allows users to document their travels and share their experiences with others. Users can register for a new account, edit their profile, and create custom maps to document the countries they have visited. Technologies used include HTML, CSS, JavaScript, Java, MySQL, Spring Boot, and Thymeleaf. Map-Share was mapped using Spring Boot, and Thymeleaf was used to generate HTML pages. RESTful APIs were used to retrieve data from the database and display it on the front end. The Mapbox API was used to display maps and FileStack API was used to upload images. This project was completed as part of the Software Development Bootcamp at Codeup and was deployed with Dokku.",
            img: "img/preview/mapshare-mbp.jpeg",
            alt: "screenshot of mapshare",
            github: "https://github.com/Mapstone-Capstone/Mapstone",
            liveSite: "https://map-share.net/",
        }
    ];

    export function handleNext() {
        if (activeIndex === projects.length - 1) {
            activeIndex = 0;
        } else {
            activeIndex++;
        }

    }

    export function handlePrev() {
        if (activeIndex === 0) {
            activeIndex = projects.length - 1;
        } else {
            activeIndex--;
        }
    }

    const title = "< Projects >";
</script>


<h2 id="projects" class="section-title">{title}</h2>
<div class="about-me-container flex-column justify-content-center align-items-center gap-5">
  <div class="increment-projects">
    <button on:click={handlePrev}>
      <span class="material-icons">arrow_back_ios</span>
    </button>
    {#key activeIndex}
      <img in:fade out:slide src="{projects[activeIndex].img}" alt="{projects[activeIndex].alt}" class="project-img">
    {/key}
    <button on:click={handleNext}>
      <span class="material-icons">arrow_forward_ios</span>
    </button>
  </div>
  <div class="project-info">
    <h3 class="project-title">{projects[activeIndex].name}</h3>
    <p class="project-description">{projects[activeIndex].description}</p>
    <div class="project-links">
      <a class="button" href="{projects[activeIndex].github}" target="_blank">
        GitHub
        <span class="material-icons">launch</span>
      </a>
      {#if projects[activeIndex].liveSite}
        <a class="button" href="{projects[activeIndex].liveSite}" target="_blank">
          Live Site
          <span class="material-icons">launch</span></a>
      {/if}
    </div>
  </div>
</div>


<style>
    .about-me-container {
        display: flex;
        flex-direction: column;
        justify-content: center;
        align-items: center;
    }

    .increment-projects {
        display: flex;
        justify-content: center;
        align-items: center;
        gap: 1rem;

        & img {
            transition: all 0.5s ease;
        }

        & button {
            display: flex;
            justify-content: center;
            align-items: center;
            font-size: 18px;
            font-family: var(--sec-font);
            color: var(--light-purple);
            cursor: pointer;
            border: 1px solid var(--light-purple);
            border-radius: 5px;

            & span {
                font-size: 50px;

                @media (max-width: 768px) {
                    font-size: 30px;
                }
            }
        }

        & button:hover {
            background-color: var(--light-purple);

            & span {
                color: white;
            }
        }

        & button:focus {
            border: 3px solid var(--light-purple);
        }


        & img {
            width: 100%;
            height: auto;

            @media (max-width: 768px) {
                width: 75%;
            }
        }
    }

    .project-info {
        display: flex;
        flex-direction: column;
        justify-content: center;
        align-items: center;
        width: 50%;

        @media (max-width: 768px) {
            width: 80%;
        }
    }

    .project-title {
        font-size: 2rem;
        font-family: var(--font);
        text-align: center;
        text-transform: uppercase;
    }

    .project-links {
        display: flex;
        justify-content: center;
        align-items: center;
        gap: 1rem;

    }


</style>