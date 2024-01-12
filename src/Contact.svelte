<script>
    const title = "< Contact Me >";

    const scriptURL = "https://script.google.com/macros/s/AKfycbwZdxUD3WdENHe4YoFyFMuwlYL3GAFlbJobEDQm0HG5Sl-r8vjkzWnKNeK3apxW1U_T/exec";
    const form = document.forms["submit-to-google-sheet"];
    let message = "";

    function submitForm() {
        message = "Sending...";
        fetch(scriptURL, {method: "POST", body: new FormData(form)})
            .then((response) => {
                console.log("Success!", response);
                message = "Thanks for reaching out! I'll get back to you soon.";
            })
            .catch((error) => {
                console.error("Error!", error.message);
                message = "Oops! Something went wrong. Please try again.";
            });
    }
    
</script>


<h2 id="contact" class="section-title">{title}</h2>
<div class="d-flex flex-column flex-xl-row contact-container gap-5">

  <div class="contact-left-column col">


    <a class="button contact-button git" href="https://github.com/jessicarosier"
       target="_blank"><img class="social-icon"
                            src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/github/github-original.svg"
                            alt="github icon"></a>
    <a class="button contact-button linkedin" href="https://www.linkedin.com/in/jessica-rosier/"
       target="_blank"><img class="social-icon"
                            src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/linkedin/linkedin-original.svg"
                            alt="facebook icon"></a>


    <a class="button contact-button resume btn resume-btn" href="img/resume/Jessica_Rosier_Resume_pdf.pdf" download><p
        class="before">Download Resume</p>
      <p class="after">👩🏽‍💻</p></a>

  </div>

  <div class="contact-right-column col">
        <span id="msg">{message}</span>
        <form name="contact" class="contact-form" method="POST" data-netlify="true">
          <input type="hidden" name="subject"
                 value="New Message from iridescent-jalebi-c7910f.netlify.app" />
          <input type="text" name="Name" placeholder="Your name" required>
          <input type="email" name="Email" placeholder="Your email" required>
          <textarea name="Message" rows="6" placeholder="Your message" required></textarea>
          <button type="button" class="button" on:click|preventDefault={() => submitForm()}>Send</button>
        </form>

  </div>
</div>


<style>
    .contact-container {
        padding: 20px;
    }

    .contact-left-column, .contact-right-column {
        display: flex;
        flex-direction: column;
        justify-content: center;
        align-items: center;
        gap: 10px;
    }

    .contact-form {
        display: flex;
        justify-content: center;
        align-items: center;
        flex-direction: column;
        gap: 20px;
        padding: 20px;
        font-family: var(--sec-font);
        font-size: 18px;
        font-weight: bolder;
        text-transform: uppercase;
        text-align: center;
        color: var(--light-purple);
        background-color: white;
        border-radius: 10px;
        width: 100%;
        border: 1px solid black;

        & label {
            font-family: var(--font);
            font-size: 30px;
            font-weight: bolder;
            text-transform: uppercase;
            text-align: center;
        }

        & input {
            width: 100%;
            padding: 10px;
            font-family: var(--font);
            font-size: 18px;
            font-weight: bolder;
            text-transform: uppercase;
            text-align: center;
            letter-spacing: 5px;
            color: var(--light-purple);
            background-color: white;
            border-radius: 10px;
            border: 1px solid black;
        }

        & textarea {
            width: 100%;
            padding: 10px;
            font-family: var(--font);
            font-size: 18px;
            font-weight: bolder;
            text-transform: uppercase;
            text-align: center;
            letter-spacing: 5px;
            color: var(--light-purple);
            background-color: white;
            border-radius: 10px;
            border: 1px solid black;
        }
    }

    .social-icon {
        height: 50px;
        width: 50px;
        margin: 10px;
        transition: transform 0.2s ease;

        &:hover {
            transform: scale(1.2);
        }
    }

    .contact-button {
        display: flex;
        justify-content: center;
        align-items: center;
        width: 50%;
        height: 100px;

    }

    .contact-button.git {
        &:hover:after {
            content: 'Check out my GitHub!';
        }
    }

    .contact-button.linkedin {
        &:hover:after {
            content: 'Connect with me on LinkedIn!';
        }
    }

    .contact-button.resume {
        text-align: center;

        & p.after {
            display: none;
        }

        &:hover {
            & p.before {
                display: none;
            }

            & p.after {
                display: block;
                font-size: 50px;
            }
        }

    }


</style>