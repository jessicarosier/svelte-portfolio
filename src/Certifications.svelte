<script>
    import {flip} from "svelte/animate";

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

    let isHovered = false;

    function handleHover() {
        isHovered = true;
    }

    function handleHoverEnd() {
        isHovered = false;
    }

    const title = "< Certifications >";
</script>

<h2 id="certs" class="section-title">{title}</h2>
<section>
  <div class="certs-container">
    {#each certifications as cert}
      <div on:mouseenter={handleHover} on:mouseleave={handleHoverEnd} class="cert-card">
        <img class="cert-img" src={cert.img} alt={cert.name}/>
        {#if isHovered}
          <a class="cert-overlay" href={cert.link} target="_blank">View Certificate</a>
        {/if}

      </div>
    {/each}
  </div>
</section>


<style>

    section {
        display: flex;
        justify-content: center;
        align-items: center;
        flex-direction: column;
        width: 100%;
    }

    .certs-container {
        display: flex;
        justify-content: center;
        align-items: center;
        flex-wrap: wrap;
        width: 50%;
    }

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
        width: 200px;

        &:hover {
            transform: scale(1.05);
        }


        & .cert-img {
            width: 150px;
            aspect-ratio: 1/1;
            object-fit: contain;

            @media (max-width: 768px) {
                width: 200px;
            }
        }

    }

    .cert-overlay {
        position: absolute;
        z-index: 1;
        width: 100%;
        height: 100%;
        top: 0;
        left: 0;
        background-color: var(--dark-purple);
        opacity: 80%;
        display: flex;
        justify-content: center;
        align-items: center;
        border-radius: 10px;
        text-decoration: none;
        color: white;
        font-family: var(--font);
        font-size: 30px;
    }


</style>