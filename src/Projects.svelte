<script>
    import {fade, scale, slide, draw} from 'svelte/transition';

    let activeIndex = 0;
    const projects = [
        {
            name: "Map-Share",
            description: "Map-Share is a full stack web application that allows users to document their travels and share their experiences with others. Users can register for a new account, edit their profile, and create custom maps to document the countries they have visited. Technologies used include HTML, CSS, JavaScript, Java, MySQL, Spring Boot, and Thymeleaf. Map-Share was mapped using Spring Boot, and Thymeleaf was used to generate HTML pages. RESTful APIs were used to retrieve data from the database and display it on the front end. The Mapbox API was used to display maps and FileStack API was used to upload images. This project was completed as part of the Software Development Bootcamp at Codeup and was deployed with Dokku.",
            img: "img/preview/mapshare-mbp.jpeg",
            alt: "screenshot of mapshare",
            github: "https://github.com/Mapstone-Capstone/Mapstone",
            liveSite: "https://map-share.net",
            tech: "Java, Spring Boot, Thymeleaf, MySQL, JavaScript, HTML, CSS, Bootstrap, Mapbox API, FileStack API"
        },
        {
            name: "Favorite Movies App",
            description: "This web app allows users to search for movies and add them to a list of favorites. The app uses the TMDB API to search for movies and retrieve movie data as well as a local JSON database to store the list of favorite movies. Technologies used include HTML, CSS, JavaScript, bootstrap, and JSON server.",
            img: "img/preview/movies-mbp.jpeg",
            alt: "screenshot of movies app",
            github: "https://github.com/jessicarosier/favorite-movies-app",
            liveSite: "https://movies-app.jessicarosier.com",
            tech: "HTML, CSS, JavaScript, Bootstrap, JSON Server, TMDB API"
        },
        {
            name: "Weather Map",
            description: "This is a weather app created using HTML, CSS, and JavaScript. The app uses the OpenWeatherMap API to retrieve weather data for a given location as well as the MapBox API to display a map of the location.",
            img: "img/preview/weather-mbp.jpeg",
            alt: "screenshot of weather app",
            github: "https://github.com/jessicarosier/weather-map",
            liveSite: "https://weather-map.jessicarosier.com",
            tech: "HTML, CSS, JavaScript, MapBox API, OpenWeatherMap API"
        },

        {
            name: "Ducklister",
            description: "Ducklister is a full stack web application that allows a niche community of jeep enthusiasts to share their love for rubber ducks. Users can register for a new account, edit their profile, list ducks they want to share, and engage with fellow duck lovers. Technologies used include HTML, CSS, JavaScript, Java, and MySQL. Ducklister was mapped using servlets, and JSPs were used to generate HTML pages. Prepared statements were used to prevent SQL injection, and BCrypt algorithm was used to hash passwords.",
            img: "img/preview/ducklister-mbp.jpeg",
            alt: "screenshot of ducklister",
            github: "https://github.com/Genesis-Luis-Jessica-Adlister/ducklister",
            tech: "Java, MySQL, JavaScript, HTML, CSS, Bootstrap"
        },
        {
            name: "Age Calculator",
            description: "This is a Frontend Mentor challenge I completed using HTML, CSS, and JavaScript. The app takes a user's birthday and calculates their age in years, months, and days.",
            img: "img/preview/age-calculator-mbp.jpeg",
            alt: "screenshot of age calculator",
            github: "https://github.com/jessicarosier/Frontend-Mentor-Projects/tree/main/age-calc-app",
            liveSite: "https://age-calculator.jessicarosier.com",
            tech: "HTML, CSS, JavaScript"
        }
    ];

    function handleNext() {
        if (activeIndex === projects.length - 1) {
            activeIndex = 0;
        } else {
            activeIndex++;
        }

    }

    function handlePrev() {
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
        <img transition:fade={{duration: 500, delay: 0}} src="{projects[activeIndex].img}" alt="{projects[activeIndex].alt}">
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
        Source Code
        <i class="devicon-github-original"></i>
      </a>
      {#if projects[activeIndex].liveSite}
        <a class="button" href="{projects[activeIndex].liveSite}" target="_blank">
          {projects[activeIndex].liveSite.split("//")[1]}
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
            background-color: transparent;
            border: unset;

            & span {
                font-size: 80px;
                font-weight: bolder;
                color: var(--light-purple);

                @media (max-width: 768px) {
                    font-size: 30px;
                }
            }
        }

        & button:hover {
            cursor: pointer;
            & span {
                transform: scale(1.5);
            }
        }


        & img {
            width: 75%;
            height: auto;
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

        @media (max-width: 768px) {
            flex-direction: column;
        }

        & a {
            height: 65px;
            display: flex;
            gap: 0.5rem;
            justify-content: center;
            align-items: center;
        }

    }


</style>