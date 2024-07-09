<script>
    import Navbar from '../components/Navbar.svelte';
</script>

<main>
    <Navbar />

    <section class="hero">
        <div class="container">
            <h1>Welcome to My Portfolio</h1>
            <p>Here, you can explore my coding skills and projects.</p>
        </div>
    </section>

    <section class="skills">
        <div class="container">
            <h2>Coding Skills</h2>
            <ul>
                <li>JavaScript</li>
                <li>HTML & CSS</li>
                <li>Svelte</li>
                <li>C++</li>
                <li>TensorFlow</li>
                <li>Python</li>
            </ul>
        </div>
    </section>

    <section class="projects">
        <div class="container">
            <h2>Projects</h2>
            <div class="project">
                <h3>Project 1</h3>
                <p>Description of Project 1. Lorem ipsum dolor sit amet, consectetur adipiscing elit.</p>
            </div>
            <div class="project">
                <h3>Project 2</h3>
                <p>Description of Project 2. Lorem ipsum dolor sit amet, consectetur adipiscing elit.</p>
            </div>
            <div class="project">
                <h3>Project 3</h3>
                <p>Description of Project 3. Lorem ipsum dolor sit amet, consectetur adipiscing elit.</p>
            </div>
        </div>
    </section>
</main>

<style>
    :global(:root) {
        --text: hsl(210, 20%, 94%);
        --background: hsl(206, 35%, 9%);
        --primary: hsl(199, 51%, 51%);
        --secondary: hsl(157, 64%, 47%);
        --accent: hsl(177, 57%, 24%);
        font-family: system-ui, -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Oxygen, Ubuntu, Cantarell, 'Open Sans', 'Helvetica Neue', sans-serif;
    }

    :global(body) {
        background-color: var(--background);
        color: var(--text);
        margin: 0;
    }

    main {
        padding: 2rem;
    }

    .container {
        max-width: 800px;
        margin: 0 auto;
        padding: 1rem;
    }

    .hero {
        text-align: center;
        padding: 4rem 1rem;
        background: var(--primary);
        color: var(--text);
        margin-bottom: 2rem;
    }

    .skills,
    .projects {
        margin-bottom: 2rem;
    }

    .skills h2,
    .projects h2 {
        font-size: 2rem;
        margin-bottom: 1rem;
        color: var(--text);
    }

    .skills ul {
        list-style: none;
        padding: 0;
        display: flex;
        flex-wrap: wrap;
        gap: 1rem;
    }

    .skills li {
        padding: 0.5rem 1rem;
        border-radius: 5px;
        color: var(--text);
        background: linear-gradient(120deg, var(--secondary), var(--accent));
        transition: transform 0.3s, box-shadow 0.3s;
        cursor: pointer;
    }

    .skills li:hover {
        transform: scale(1.05);
        box-shadow: 0 4px 8px rgba(0, 0, 0, 0.2);
    }

    .projects .project {
        background: var(--accent);
        padding: 1rem;
        border-radius: 5px;
        margin-bottom: 1rem;
        color: var(--text);
        transition: transform 0.3s, box-shadow 0.3s;
        cursor: pointer;
    }

    .projects .project:hover {
        transform: scale(1.05);
        box-shadow: 0 4px 8px rgba(0, 0, 0, 0.2);
    }

    .projects .project h3 {
        margin: 0;
        font-size: 1.5rem;
        color: var(--text);
    }

    .projects .project p {
        margin: 0.5rem 0 0;
    }
</style>
