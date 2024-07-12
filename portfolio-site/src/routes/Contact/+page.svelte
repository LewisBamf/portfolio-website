<script>
    import Navbar from '$lib/components/Navbar.svelte';
    import Footer from '$lib/components/Footer.svelte';
    import '../../global.css';
    import emailjs from 'emailjs-com';

    let name = '';
    let email = '';
    let message = '';
    let formStatus = '';

    // Your EmailJS credentials
    const userID = 'P7eMt7bCfLsHvsOLl'; // Public Key (User ID)
    const serviceID = 'service_pumui4p';  // Service ID
    const templateID = 'template_lj5pn4n';  // Template ID

    // Handle form submission
    // @ts-ignore
    const handleSubmit = async (event) => {
        event.preventDefault();

        if (!name || !email || !message) {
            formStatus = 'Please fill out all fields.';
            return;
        }

        try {
            // Send email using EmailJS
            await emailjs.send(serviceID, templateID, {
                from_name: name,
                from_email: email,
                message: message,
            }, userID);

            formStatus = 'Thank you for reaching out! I will get back to you soon.';
            name = '';
            email = '';
            message = '';
        } catch (error) {
            formStatus = 'Sorry, there was a problem sending your message.';
            console.error('EmailJS Error:', error);
        }
    };
</script>

<main>
    <section class="hero">
        <div class="container">
            <h1>Contact Me</h1>
            <p>I’d love to hear from you! Feel free to reach out using the form below or connect with me on social media.</p>
        </div>
    </section>

    <section class="contact-form">
        <div class="container">
            <h2>Get in Touch</h2>
            <form on:submit={handleSubmit}>
                <label for="name">Name:</label>
                <input type="text" id="name" bind:value={name} placeholder="Your Name" required />

                <label for="email">Email:</label>
                <input type="email" id="email" bind:value={email} placeholder="Your Email" required />

                <label for="message">Message:</label>
                <textarea id="message" bind:value={message} placeholder="Your Message" required></textarea>

                <button type="submit" class="animated-button">
                    <span class="shadow"></span>
                    <span class="edge"></span>
                    <span class="front text">Send Message</span>
                </button>

                {#if formStatus}
                    <p class={formStatus === 'Thank you for reaching out! I will get back to you soon.' ? 'success' : 'error'}>{formStatus}</p>
                {/if}
            </form>
        </div>
    </section>



    <Navbar />
    <Footer />
</main>

<style>
    main {
        padding: 2rem;
        padding-left: 0%;
        padding-right: 0%;
    }
    
    .container {
        max-width: 900px;
        margin: 0 auto;
        padding: 2rem 1rem;
    }
    
    .hero {
        text-align: center;
        padding: 6rem 1rem;
        background: linear-gradient(360deg, var(--background), var(--accent));
        color: var(--text);
        margin-bottom: 2rem;
    }
    
    .hero h1 {
        font-family: var(--heading-font);
        font-size: 3rem;
        margin: 0 0 1rem 0;
    }
    
    .hero p {
        font-size: 1.25rem;
    }
    
    .contact-form {
        margin-bottom: 3rem;
    }
    
    .contact-form h2 {
        font-size: 2.5rem;
        margin-bottom: 1rem;
        color: var(--text);
        font-family: var(--heading-font);
    }
    
    .contact-form form {
        display: flex;
        flex-direction: column;
        gap: 1rem;
    }
    
    .contact-form label {
        font-size: 1rem;
    }
    
    .contact-form input,
    .contact-form textarea {
        padding: 0.75rem;
        border-radius: 8px;
        border: 1px solid var(--text);
        background: var(--background);
        color: var(--text);
        font-size: 1rem;
    }
    
    .contact-form textarea {
        resize: vertical;
        min-height: 100px;
    }
    
    .animated-button {
        position: relative;
        border: none;
        background: transparent;
        padding: 0;
        cursor: pointer;
        outline-offset: 4px;
        transition: filter 250ms;
        user-select: none;
        touch-action: manipulation;
    }
    
    .animated-button .shadow {
        position: absolute;
        top: 0;
        left: 0;
        width: 100%;
        height: 100%;
        border-radius: 8px; /* Keep the existing border-radius */
        background: hsl(0deg 0% 0% / 0.25);
        will-change: transform;
        transform: translateY(2px);
        transition: transform 600ms cubic-bezier(.3, .7, .4, 1);
    }
    
    .animated-button .edge {
        position: absolute;
        top: 0;
        left: 0;
        width: 100%;
        height: 100%;
        border-radius: 8px; /* Keep the existing border-radius */
        background: linear-gradient(
             to left,
             hsl(204, 70%, 20%) 0%,
             hsl(204, 70%, 40%) 8%,
             hsl(204, 70%, 40%) 92%,
             hsl(204, 70%, 20%) 100%
        );

    }
    
    .animated-button .front {
        display: block;
        position: relative;
        padding: 0.75rem; /* Keep the existing padding */
        border-radius: 8px; /* Keep the existing border-radius */
        font-size: 1rem; /* Keep the existing font size */
        color: white;
        background: var(--primary); /* Keep the existing background color */
        will-change: transform;
        transform: translateY(-4px);
        transition: transform 600ms cubic-bezier(.3, .7, .4, 1);
    }
    
    .animated-button:hover {
        filter: brightness(110%);
    }
    
    .animated-button:hover .front {
        transform: translateY(-6px);
        transition: transform 250ms cubic-bezier(.3, .7, .4, 1.5);
    }
    
    .animated-button:active .front {
        transform: translateY(-2px);
        transition: transform 34ms;
    }
    
    .animated-button:hover .shadow {
        transform: translateY(4px);
        transition: transform 250ms cubic-bezier(.3, .7, .4, 1.5);
    }
    
    .animated-button:active .shadow {
        transform: translateY(1px);
        transition: transform 34ms;
    }
    
    .animated-button:focus:not(:focus-visible) {
        outline: none;
    }
    
    .contact-form p {
        font-size: 1rem;
        margin: 1rem 0 0;
    }
    
    .contact-form .error {
        color: red;
    }
    
    .contact-form .success {
        color: green;
    }

    

@media (max-width: 600px) {
    .hero h1 {
        font-size: 2.5rem;
    }
    .hero p {
        font-size: 1rem;
    }
    .contact-form h2{
        font-size: 2rem;
    }
}
    </style>
