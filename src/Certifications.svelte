<script>
    const certifications = [
        {
            name: "Securtiy+",
            link: "https://www.credly.com/badges/469f4921-f554-4952-9365-c89947f5c373/public_url",
            img: "img/certs/sec_plus.png",
        },
        {
            name: "Cloud+",
            link: "https://www.credly.com/badges/0b165358-b5c7-4423-8170-c21a5278f2d4/public_url",
            img: "img/certs/cloud_plus.png",
        },
        {
            name: "Network+",
            link: "https://www.credly.com/badges/6ee6a226-61b4-4a86-a714-3db9ebea20e1/public_url",
            img: "img/certs/network_plus.png",
        },
        {
            name: "Server+",
            link: "https://www.credly.com/badges/a9756f7e-7749-4aff-bde8-c5a89e9785c3/public_url",
            img: "img/certs/server_plus.png",
        },
        {
            name: "Microsoft Certified: Azure Fundamentals",
            link: "https://www.credly.com/badges/5fc16da2-789f-4f3f-b364-d7f1036636c7/public_url",
            img: "img/certs/azure_fundamentals.png",
        },
        {
            name: "AWS Certified Cloud Practitioner",
            link: "https://www.credly.com/badges/726fc5d4-c2b3-494a-b135-be48817d1bee/public_url",
            img: "img/certs/aws_practitioner.png",
        }
    ];

    let skills = [
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
        }
    ];



</script>

{#each certifications as cert}
<div class="cert-card">
  <img class="cert-img" src={cert.img} alt={cert.name} />
  <a class="cert-overlay" href={cert.link} target="_blank">View Certificate</a>
</div>
{/each}

<style>
    .cert-card {
        margin: 20px;
        padding: 20px;
        display: flex;
        justify-content: center;
        align-items: center;
        flex-direction: column;
        background-color: #fff;
        border-radius: 10px;
        font-size: 18px;
        font-family: var(--sec-font);

        &:hover {
            transform: scale(1.05);
        }


        & .cert-img {
            width: 500px;
            aspect-ratio: 1/1;
            object-fit: contain;

            @media (max-width: 768px) {
                width: 200px;
            }
        }

    }


</style>