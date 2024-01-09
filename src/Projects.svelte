<script>
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

</script>

<div class="about-me-container flex-column justify-content-center align-items-center gap-5">
  {#each projects as project}
    <img src="{project.img}" alt="{project.alt}" class="project-img">
    <div class="project-info">
      <h3 class="project-title">{project.name}</h3>
      <p class="project-description">{project.description}</p>
      <div class="project-links">
        <a class="button" href="{project.github}" target="_blank">GitHub</a>
        {#if project.liveSite}
          <a class="button" href="{project.liveSite}" target="_blank">Live Site</a>
        {/if}

      </div>
      </div>
  {/each}

</div>


<style>

</style>