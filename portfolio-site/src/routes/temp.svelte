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
        --primary: hsl(199, 60%, 50%);
        --secondary: hsl(157, 64%, 40%);
        --accent: hsl(177, 57%, 32%);
        --hover-accent: hsl(177, 57%, 40%);
        --shadow: rgba(0, 0, 0, 0.2);
        --border-radius: 8px;
        font-family: 'Open Sans', 'Helvetica Neue', sans-serif;
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
        border-radius: var(--border-radius);
        box-shadow: 0 8px 16px var(--shadow);
    }

    .skills,
    .projects {
        margin-bottom: 2rem;
    }

    .skills h2,
    .projects h2 {
        font-size: 2.5rem;
        margin-bottom: 1.5rem;
        color: var(--primary);
        text-align: center;
    }

    .skills ul {
        list-style: none;
        padding: 0;
        display: flex;
        flex-wrap: wrap;
        gap: 1rem;
        justify-content: center;
    }

    .skills li {
        padding: 0.75rem 1.25rem;
        border-radius: var(--border-radius);
        color: var(--text);
        background: linear-gradient(135deg, var(--secondary), var(--accent));
        transition: transform 0.3s, box-shadow 0.3s;
        cursor: pointer;
    }

    .skills li:hover {
        transform: scale(1.05);
        box-shadow: 0 4px 8px var(--shadow);
    }

    .projects .project {
        background: var(--accent);
        padding: 1.5rem;
        border-radius: var(--border-radius);
        margin-bottom: 1.5rem;
        color: var(--text);
        transition: transform 0.3s, box-shadow 0.3s;
        cursor: pointer;
    }

    .projects .project:hover {
        transform: scale(1.05);
        box-shadow: 0 4px 8px var(--shadow);
    }

    .projects .project h3 {
        margin: 0;
        font-size: 1.75rem;
        color: var(--text);
    }

    .projects .project p {
        margin: 0.75rem 0 0;
    }
</style>