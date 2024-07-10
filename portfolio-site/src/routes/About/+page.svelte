<script>
    export const data = null;
    import Navbar from '$lib/components/Navbar.svelte';
</script>

<main>

    <section class="hero">
        <div class="container">
            <h1>About Me</h1>
            <p>Hello! I’m Lewis, a young developer from the UK.</p>
        </div>
    </section>

    <section class="intro">
        <div class="container">
            <h2>My Journey</h2>
            <p>I’m a 16-year-old coder with a passion for technology and innovation. I started programming as a hobby and quickly fell in love with it. My focus areas are web development, machine learning, and game development. I enjoy working on projects that challenge me and allow me to learn new skills.</p>
            <p>In addition to coding, I like exploring new tech trends, participating in coding challenges, and contributing to open-source projects. I’m always on the lookout for exciting opportunities to grow and make a difference in the tech world.</p>
        </div>
    </section>

    <section class="skills">
        <div class="container">
            <h2>Skills & Technologies</h2>
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
            <h2>Featured Projects</h2>
            <div class="project">
                <h3>Project 1</h3>
                <p>A brief overview of a cool project I worked on. It demonstrates my skills in coding and problem-solving.</p>
            </div>
            <div class="project">
                <h3>Project 2</h3>
                <p>Another exciting project showcasing my abilities in creating functional and innovative solutions.</p>
            </div>
            <div class="project">
                <h3>Project 3</h3>
                <p>A look at a recent project that highlights my commitment to learning and improving as a developer.</p>
            </div>
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

.intro {
    margin-bottom: 3rem;
}

.intro h2 {
    font-size: 2.5rem;
    margin-bottom: 1rem;
    color: var(--text);
    font-family: var(--heading-font);
}

.intro p {
    font-size: 1rem;
    line-height: 1.6;
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
    background: linear-gradient(120deg, var(--secondary), var(--primary));
    transition: transform 0.3s, box-shadow 0.3s;
    cursor: pointer;
}

.skills li:hover {
    transform: scale(1.1);
    box-shadow: 0 6px 12px var(--shadow);
}

.projects .project {
    background: var(--primary);
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
    .intro h2,
    .skills h2,
    .projects h2 {
        font-size: 2rem;
    }
}
</style>
