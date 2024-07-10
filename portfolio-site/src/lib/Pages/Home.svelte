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
    --text: hsl(210, 15%, 95%); /* Lighter text for better contrast */
    --background: hsl(210, 30%, 10%); /* Slightly cooler and darker background */
    --primary: hsl(204, 70%, 53%); /* A bit more vibrant and tech-inspired */
    --secondary: hsl(160, 55%, 45%); /* Softer, complementary secondary color */
    --accent: hsl(190, 50%, 30%); /* Muted teal for a subtle accent */
    --shadow: hsla(0, 2%, 11%, 0.518); /* Darker color for shadows */
    --heading-font: 'Poppins', sans-serif;
    --body-font: 'Roboto', sans-serif;
}


:global(body) {
    background-color: var(--background);
    color: var(--text);
    margin: 0;
    font-family: var(--body-font);
}

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

.skills,
.projects {
    margin-bottom: 3rem;
}

.skills h2,
.projects h2 {
    font-size: 2.5rem;
    margin-bottom: 1rem;
    color: var(--text);
    font-family: var(--heading-font);
}

.skills ul {
    list-style: none;
    padding: 0;
    display: flex;
    flex-wrap: wrap;
    gap: 1rem;
}

.skills li {
    padding: 0.75rem 1.5rem;
    border-radius: 8px;
    color: var(--text);
    background: linear-gradient(120deg, var(--secondary), var(--accent));
    transition: transform 0.3s, box-shadow 0.3s;
    cursor: pointer;
}

.skills li:hover {
    transform: scale(1.1);
    box-shadow: 0 6px 12px var(--shadow);
}

.projects .project {
    background: var(--accent);
    padding: 1.5rem;
    border-radius: 8px;
    margin-bottom: 1.5rem;
    color: var(--text);
    transition: transform 0.3s, box-shadow 0.3s;
    cursor: pointer;
}

.projects .project:hover {
    transform: scale(1.05);
    box-shadow: 0 6px 12px rgba(0, 0, 0, 0.3);
}

.projects .project h3 {
    margin: 0;
    font-size: 1.75rem;
    color: var(--text);
}

.projects .project p {
    margin: 0.75rem 0 0;
}

@media (max-width: 600px) {
    .hero h1 {
        font-size: 2.5rem;
    }
    .hero p {
        font-size: 1rem;
    }
    .skills h2,
    .projects h2 {
        font-size: 2rem;
    }
}
</style>
