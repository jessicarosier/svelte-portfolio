<script>
    const title = "< About Me >";
</script>


<h2 id="about" class="section-title">{title}</h2>
<div class="about-me-container d-flex flex-column flex-xl-row justify-content-center align-items-center">

  <div class="d-flex flex-column align-items-center">
    <div class="image-wrapper d-inline-block overflow-hidden object-fit-cover">
      <img class="w-100" src="img/jess1.jpeg"
           alt="Jessica Rosier">
    </div>
  </div>
  <div class="d-flex flex-column align-items-center aboutMeText">
    <p>
      Hello there!
      I'm
      <strong>Jessica Rosier</strong>,
      <br>
      a passionate full stack web developer on a mission to
      create beautiful, functional, and user-friendly applications.
      <br>
      Before diving into the world of web development, I voyaged across the seas 🌊 while serving in the
      United States Navy as an Information Systems Technician where I managed networks and
      ensured optimal performance of systems and equipment.
      <br>
      I've uncovered my true passion in web development — a realm where I can seamlessly blend my technical
      expertise with creativity! I'm excited to embark on a career journey where I can continue to learn and
      grow as a developer and make a positive impact through code and design.
      <br>
    </p>
  </div>

</div>


<style>

    strong {
        color: cornflowerblue;
    }

    h2 {
        background-color: var(--dark-purple);
        color: white;
        margin-bottom: 0;
        padding: 20px 0;
    }


    .about-me-container {
        background-color: var(--dark-purple);
        font-family: var(--font);
        text-transform: uppercase;
        font-size: 2rem;
        font-weight: 600;
        color: white;
        padding: 50px 0;
        text-align: center;

        gap: 10px;

        @media (max-width: 768px) {

            gap: 20px;
        }
    }

    .aboutMeText {

        & p {
            width: 800px;
            font-size: 1.5rem;
            text-transform: capitalize;

            @media (max-width: 768px) {
                width: 100%;
                padding: 0 20px;
            }
        }
    }

    .image-wrapper {
        width: 275px;
        height: 275px;
        border-radius: 50%;
    }

    .image-wrapper img {
        height: auto;
        margin-top: -55px;

        &:hover {
            cursor: pointer;
            height: auto;
            margin-top: -55px;
        }


    }


</style>