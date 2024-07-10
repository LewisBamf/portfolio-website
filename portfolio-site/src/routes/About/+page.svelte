<script>
    export const data = null;
    import Navbar from '$lib/components/Navbar.svelte';
    import Footer from '$lib/components/Footer.svelte';
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
            <div class="skills-categories">
                <div class="category">
                    <h3>Languages</h3>
                    <ul>
                        <li>JavaScript</li>
                        <li>HTML & CSS</li>
                        <li>C++</li>
                        <li>Python</li>
                        <li>Vue</li>
                    </ul>
                </div>
                <div class="category">
                    <h3>Libraries</h3>
                    <ul>
                        <li>Svelte</li>
                        <li>TensorFlow</li>
                        <li>SFML</li>
                        <li>NumPy</li>
                        <li>Unity</li>
                        <li>Open GL</li>
                        <li>Matplotlib</li>
                        <li>Scikit-Learn</li>
                        <li>Pandas</li>
                        <li>Keras</li>
                    </ul>
                </div>
                <div class="category">
                    <h3>Technologies</h3>
                    <ul>
                        <li>Web Development</li>
                        <li>Machine Learning</li>
                        <li>Game Development</li>
                        <li>Mobile Development</li>
                        <li>Version Control (Git)</li>
                        <li>APIs</li>
                        <li>Data Visualization</li>
                    </ul>
                </div>
                <div class="category">
                    <h3>Other</h3>
                    <ul>
                        <ul>
                            <li><strong>Problem Solving:</strong> Tackling challenges with creative solutions.</li>
                            <li><strong>Open Source Contribution:</strong> Making a difference in open source projects.</li>
                            <li><strong>Code Challenges:</strong> Thriving in coding competitions.</li>
                            <li><strong>Tech News:</strong> Always up-to-date with the latest tech trends.</li>
                            <li><strong>Project Management:</strong> Leading projects to success.</li>
                            <li><strong>Team Collaboration:</strong> Working well with others.</li>
                            <li><strong>Communication Skills:</strong> Sharing ideas clearly and effectively.</li>
                            <li><strong>Time Management:</strong> Organizing time for maximum productivity.</li>
                        </ul>                        
                    </ul>
                </div>
            </div>
        </div>
    </section>

    <Navbar />
    <Footer />
</main>

<style>
:global(:root) {
    --text: hsl(210, 15%, 95%);
    --background: hsl(210, 30%, 10%);
    --primary: hsl(204, 70%, 53%);
    --secondary: hsl(160, 55%, 45%);
    --accent: hsl(190, 50%, 30%);
    --shadow: hsla(0, 2%, 11%, 0.518);
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

.skills {
    margin-bottom: 3rem;
}

.skills h2 {
    font-size: 2.5rem;
    margin-bottom: 1rem;
    color: var(--text);
    font-family: var(--heading-font);
}

.skills-categories {
    display: flex;
    flex-wrap: wrap;
    gap: 2rem;
}

.category {
    flex: 1;
    min-width: 200px;
}

.category h3 {
    font-size: 2rem;
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

@media (max-width: 600px) {
    .hero h1 {
        font-size: 2.5rem;
    }
    .hero p {
        font-size: 1rem;
    }
    .intro h2,
    .skills h2 {
        font-size: 2rem;
    }
}
</style>
