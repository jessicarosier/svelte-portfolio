<script>

    const skills = [
        {
            name: "HTML",
            icon: "https://cdn.jsdelivr.net/gh/devicons/devicon/icons/html5/html5-original.svg",
            type: "front-end"
        },
        {
            name: "CSS",
            icon: "https://cdn.jsdelivr.net/gh/devicons/devicon/icons/css3/css3-original.svg",
            type: "front-end"
        },
        {
            name: "JavaScript",
            icon: "https://cdn.jsdelivr.net/gh/devicons/devicon/icons/javascript/javascript-original.svg",
            type: "front-end"
        },
        {
            name: "jQuery",
            icon: "https://cdn.jsdelivr.net/gh/devicons/devicon/icons/jquery/jquery-original.svg",
            type: "front-end"
        },
        {
            name: "Bootstrap",
            icon: "https://cdn.jsdelivr.net/gh/devicons/devicon/icons/bootstrap/bootstrap-plain.svg",
            type: "front-end"
        },
        {
            name: "Java",
            icon: "https://cdn.jsdelivr.net/gh/devicons/devicon/icons/java/java-plain.svg",
            type: "back-end"
        },
        {
            name: "mySQL",
            icon: "https://cdn.jsdelivr.net/gh/devicons/devicon/icons/mysql/mysql-original.svg",
            type: "back-end"
        },
        {
            name: "Spring Boot",
            icon: "https://cdn.jsdelivr.net/gh/devicons/devicon/icons/spring/spring-original.svg",
            type: "back-end"
        },

        {
            name: "GitHub",
            icon: "https://cdn.jsdelivr.net/gh/devicons/devicon/icons/github/github-original.svg",
            type: "tools"
        },
        {
            name: "NPM",
            icon: "https://cdn.jsdelivr.net/gh/devicons/devicon/icons/npm/npm-original-wordmark.svg",
            type: "tools"
        },
        {
            name: "Azure",
            icon: "https://cdn.jsdelivr.net/gh/devicons/devicon/icons/azure/azure-original.svg",
            type: "tools"
        },
        {
            name: "AWS",
            icon: "https://cdn.jsdelivr.net/gh/devicons/devicon/icons/amazonwebservices/amazonwebservices-original.svg",
            type: "tools"
        },
        {
            name: "Linux",
            icon: "https://cdn.jsdelivr.net/gh/devicons/devicon/icons/linux/linux-original.svg",
            type: "tools"
        },
        {
            name: "VS Code",
            icon: "https://cdn.jsdelivr.net/gh/devicons/devicon/icons/vscode/vscode-original.svg",
            type: "tools"
        },
        {
            name: "Svelte",
            icon: "https://cdn.jsdelivr.net/gh/devicons/devicon/icons/svelte/svelte-original.svg",
            type: "front-end"
        }
    ];

    const title = "< Tech Toolbox >";

</script>


<h2 id="skills" class="section-title"> {title} </h2>
<div class="d-flex flex-column skills-container flex-xl-row" id="skills">
  <section class="skills-col">
    <h3 class="skills-col-title text-center">Front End</h3>
    <div class="front-end-skills wrap-skills">
      {#each skills.filter(skill => skill.type === "front-end") as skill}
        <div class="skill-card">
          <img class="skill-icon" src={skill.icon} alt={skill.name}/>
          <p class="skill-name">{skill.name}</p>
        </div>
      {/each}
    </div>
  </section>


  <section class="skills-col">
    <h3 class="skills-col-title text-center">Back End</h3>
    <div class="back-end-skills wrap-skills">
      {#each skills.filter(skill => skill.type === "back-end") as skill}
        <div class="skill-card">
          <img class="skill-icon" src={skill.icon} alt={skill.name}/>
          <p class="skill-name">{skill.name}</p>
        </div>
      {/each}
    </div>
  </section>


  <section class="skills-col">
    <h3 class="skills-col-title text-center">Tools</h3>
    <div class="tools wrap-skills">
      {#each skills.filter(skill => skill.type === "tools") as skill}
        <div class="skill-card">
          <img class="skill-icon" src={skill.icon} alt={skill.name}/>
          <p class="skill-name">{skill.name}</p>
        </div>
      {/each}
    </div>
  </section>

</div>


<style>

    h2 {

        margin-bottom: 0;
        padding: 20px 0;
        background-color: var(--dark-purple);
        color: white;
    }

    .skills-container {
        justify-content: center;
        align-items: center;
        gap: 20px;
        background-color: var(--dark-purple);
        padding-top: 20px;
        padding-bottom: 40px;

    }

    .skills-col {
        padding: 0;
        display: flex;
        flex-direction: column;
        gap: 20px;
        color: white;
        font-family: var(--font);
        font-size: 30px;
        font-weight: bolder;
        text-transform: uppercase;
        text-align: center;
        border: 1px solid white;
        border-radius: 10px;
        width: 500px;
        height: 500px;


        @media (max-width: 768px) {
            width: 90%;
            height: 100%;
        }


        & .skills-col-title {
            font-family: var(--font);
            font-size: 30px;
            color: black;
            font-weight: bolder;
            text-transform: uppercase;
            text-align: center;
            margin: 0;

        }

    }

    .wrap-skills {
        display: flex;
        justify-content: center;
        align-items: center;
        flex-wrap: wrap;
        gap: 20px;
        padding: 20px;
        color: white;
        font-family: var(--font);
        font-size: 30px;
        font-weight: bolder;
        text-transform: uppercase;
        text-align: center;

    }

    .skill-card {
        display: flex;
        justify-content: center;
        align-items: center;
        flex-direction: column;
        gap: 20px;
        font-size: 18px;
        font-family: var(--sec-font);
        max-width: 150px;


        & .skill-icon {
            width: 30%;
            aspect-ratio: 1/1;
            object-fit: contain;

            @media (max-width: 768px) {
                width: 50%;
            }
        }

        & .skill-name {
            font-family: var(--font);
            font-size: 30px;
            font-weight: bolder;
            text-transform: uppercase;
            text-align: center;

            @media (max-width: 768px) {
                font-size: 20px;
            }
        }


    }


</style>