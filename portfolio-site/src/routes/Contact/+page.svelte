<script>
    import Navbar from '$lib/components/Navbar.svelte';

    let name = '';
    let email = '';
    let message = '';
    let formStatus = '';

    const handleSubmit = async (event) => {
        event.preventDefault();

        // Basic form validation
        if (!name || !email || !message) {
            formStatus = 'Please fill out all fields.';
            return;
        }

        // Dummy form submission - replace with your actual form handler
        formStatus = 'Thank you for reaching out! I will get back to you soon.';
        name = '';
        email = '';
        message = '';
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
                <input type="text" id="name" bind:value={name} placeholder="Your Name" />

                <label for="email">Email:</label>
                <input type="email" id="email" bind:value={email} placeholder="Your Email" />

                <label for="message">Message:</label>
                <textarea id="message" bind:value={message} placeholder="Your Message"></textarea>

                <button type="submit">Send Message</button>

                {#if formStatus}
                    <p class={formStatus === 'Thank you for reaching out! I will get back to you soon.' ? 'success' : 'error'}>{formStatus}</p>
                {/if}
            </form>
        </div>
    </section>

    <section class="social-media">
        <div class="container">
            <h2>Connect with Me</h2>
            <ul>
                <li><a href="https://github.com/yourusername" target="_blank" rel="noopener noreferrer">GitHub</a></li>
                <li><a href="https://twitter.com/yourusername" target="_blank" rel="noopener noreferrer">Twitter</a></li>
                <li><a href="https://linkedin.com/in/yourusername" target="_blank" rel="noopener noreferrer">LinkedIn</a></li>
            </ul>
        </div>
    </section>

    <Navbar />
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
    background: linear-gradient(360deg, var(--background), var(--primary));
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

.contact-form button {
    padding: 0.75rem;
    border-radius: 8px;
    border: none;
    background: var(--primary);
    color: var(--text);
    font-size: 1rem;
    cursor: pointer;
    transition: background 0.3s, box-shadow 0.3s;
}

.contact-form button:hover {
    background: hsl(204, 70%, 63%);
    box-shadow: 0 4px 8px var(--shadow);
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

.social-media {
    margin-bottom: 3rem;
}

.social-media h2 {
    font-size: 2.5rem;
    margin-bottom: 1rem;
    color: var(--text);
    font-family: var(--heading-font);
}

.social-media ul {
    list-style: none;
    padding: 0;
    display: flex;
    flex-direction: column;
    gap: 1rem;
}

.social-media li {
    font-size: 1.25rem;
}

.social-media a {
    color: var(--primary);
    text-decoration: none;
}

.social-media a:hover {
    text-decoration: underline;
}

@media (max-width: 600px) {
    .hero h1 {
        font-size: 2.5rem;
    }
    .hero p {
        font-size: 1rem;
    }
    .contact-form h2,
    .social-media h2 {
        font-size: 2rem;
    }
}
</style>
