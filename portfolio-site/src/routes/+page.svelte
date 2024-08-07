<script lang="ts">
    import Footer from '$lib/components/Footer.svelte';
    import Navbar from '../lib/components/Navbar.svelte';
    import '../global.css';
    import MongoDB from '../assets/1720864136354-911aff36-81a7-4397-ace0-307135cc8633_1.jpg';
    import { goto } from '$app/navigation';

    let isOpen = false;

    async function showMore() {
        await goto('/About');
        setTimeout(() => {
            window.scrollTo(0, document.body.scrollHeight / 3);
        }, 100);
    }

    async function DiscoverProjects() {
        await goto('/Projects');
    }

    function toggleCertificate() {
        isOpen = !isOpen;
    }

    function toggleCertificateContainer() {
        if (isOpen == true) {
            isOpen = false;
        }
    }
</script>

<main>
    <section class="hero">
        <div class="container">
            <h1 class="animate-title">Welcome to My Portfolio</h1>
            <p class="animate-subtitle">Here, you can explore my coding skills and projects.</p>
            <button on:click={DiscoverProjects} class="hero-button">Discover Projects</button>
        </div>
    </section>

    <section class='certificates'>
        <div class="container">
            <h2>Certificates</h2>
            <h3>MongoDB</h3>
            <!-- svelte-ignore a11y-no-static-element-interactions -->
            <!-- svelte-ignore a11y-click-events-have-key-events -->
            <!-- svelte-ignore missing-declaration -->
            <div class="certificate-container" on:click={toggleCertificateContainer} class:open={isOpen}>
                <!-- svelte-ignore a11y-no-noninteractive-element-interactions -->
                <!-- svelte-ignore a11y-click-events-have-key-events -->
                <img src={MongoDB} alt="MongoDB certificate" class="certificate" on:click|stopPropagation={toggleCertificate} />
            </div>
        </div>
    </section>

    <section class="skills">
        <div class="container">
            <h2>Coding Skills</h2>
            <!-- svelte-ignore a11y-no-noninteractive-element-interactions -->
            <ul>
                <li>JavaScript</li>
                <li>HTML & CSS</li>
                <li>Svelte</li>
                <li>C++</li>
                <li>TensorFlow</li>
                <li>Python</li>
                <!-- svelte-ignore a11y-click-events-have-key-events -->
                <li class="show-more" on:click={showMore}>Show more...</li>
            </ul>
        </div>
    </section>

    <section class="projects">
        <div class="container">
            <h2>Projects</h2>
            <div class="project">
                <h3>Verlet Physics Simulator</h3>
                <p>A physics simulator that uses Verlet integration to model rigid body dynamics and collisions in 2D space.</p>
                <a href="https://github.com/LewisBamf/Verlet-Physics-sim" target="_blank" class="github-link">
                    <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" fill="currentColor" class="github-icon">
                        <path d="M12 0C5.372 0 0 5.373 0 12c0 5.308 3.438 9.808 8.207 11.39.6.111.82-.26.82-.578 0-.286-.01-1.046-.015-2.057-3.338.725-4.04-1.606-4.04-1.606-.545-1.384-1.333-1.751-1.333-1.751-1.088-.743.083-.728.083-.728 1.205.084 1.838 1.236 1.838 1.236 1.07 1.836 2.809 1.305 3.493.998.107-.775.418-1.305.763-1.605-2.665-.303-5.466-1.332-5.466-5.928 0-1.31.469-2.381 1.24-3.222-.125-.303-.538-1.52.115-3.175 0 0 1.01-.323 3.3 1.228.957-.266 1.981-.399 3.001-.404 1.02.005 2.046.138 3.002.404 2.291-1.551 3.297-1.228 3.297-1.228.653 1.655.241 2.872.116 3.175.77.841 1.237 1.912 1.237 3.222 0 4.605-2.804 5.622-5.473 5.922.43.371.815 1.104.815 2.224 0 1.606-.015 2.913-.015 3.303 0 .319.22.694.825.578A12.026 12.026 0 0024 12c0-6.627-5.373-12-12-12z"/>
                    </svg>
                </a>
            </div>
            <div class="project">
                <h3>Using TensorFlow to Solve the MNIST Database</h3>
                <p>A simple neural network using TensorFlow to classify handwritten digits from the MNIST database.</p>
                <a href="https://github.com/LewisBamf/tensorflow-test-Greyscale-Handdrawn-Images" target="_blank" class="github-link">
                    <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" fill="currentColor" class="github-icon">
                        <path d="M12 0C5.372 0 0 5.373 0 12c0 5.308 3.438 9.808 8.207 11.39.6.111.82-.26.82-.578 0-.286-.01-1.046-.015-2.057-3.338.725-4.04-1.606-4.04-1.606-.545-1.384-1.333-1.751-1.333-1.751-1.088-.743.083-.728.083-.728 1.205.084 1.838 1.236 1.838 1.236 1.07 1.836 2.809 1.305 3.493.998.107-.775.418-1.305.763-1.605-2.665-.303-5.466-1.332-5.466-5.928 0-1.31.469-2.381 1.24-3.222-.125-.303-.538-1.52.115-3.175 0 0 1.01-.323 3.3 1.228.957-.266 1.981-.399 3.001-.404 1.02.005 2.046.138 3.002.404 2.291-1.551 3.297-1.228 3.297-1.228.653 1.655.241 2.872.116 3.175.77.841 1.237 1.912 1.237 3.222 0 4.605-2.804 5.622-5.473 5.922.43.371.815 1.104.815 2.224 0 1.606-.015 2.913-.015 3.303 0 .319.22.694.825.578A12.026 12.026 0 0024 12c0-6.627-5.373-12-12-12z"/>
                    </svg>
                </a>
            </div>
            <div class="project">
                <h3>Personal Portfolio</h3>
                <p>My own portfolio website built with Svelte to showcase my skills and projects.</p>
                <a href="https://github.com/LewisBamf/portfolio-website" target="_blank" class="github-link">
                    <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" fill="currentColor" class="github-icon">
                        <path d="M12 0C5.372 0 0 5.373 0 12c0 5.308 3.438 9.808 8.207 11.39.6.111.82-.26.82-.578 0-.286-.01-1.046-.015-2.057-3.338.725-4.04-1.606-4.04-1.606-.545-1.384-1.333-1.751-1.333-1.751-1.088-.743.083-.728.083-.728 1.205.084 1.838 1.236 1.838 1.236 1.07 1.836 2.809 1.305 3.493.998.107-.775.418-1.305.763-1.605-2.665-.303-5.466-1.332-5.466-5.928 0-1.31.469-2.381 1.24-3.222-.125-.303-.538-1.52.115-3.175 0 0 1.01-.323 3.3 1.228.957-.266 1.981-.399 3.001-.404 1.02.005 2.046.138 3.002.404 2.291-1.551 3.297-1.228 3.297-1.228.653 1.655.241 2.872.116 3.175.77.841 1.237 1.912 1.237 3.222 0 4.605-2.804 5.622-5.473 5.922.43.371.815 1.104.815 2.224 0 1.606-.015 2.913-.015 3.303 0 .319.22.694.825.578A12.026 12.026 0 0024 12c0-6.627-5.373-12-12-12z"/>
                    </svg>
                </a>
            </div>
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
    position: relative;
    overflow: hidden;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
}

.hero h1 {
    font-family: var(--heading-font);
    font-size: 3rem;
    margin: 0 0 1rem 0;
    opacity: 0;
    animation: fadeIn 1s forwards, slideInFromTop 1s forwards;
}

.hero p {
    font-size: 1.25rem;
    opacity: 0;
    animation: fadeIn 1.5s forwards, slideInFromBottom 1.5s forwards;
}

.hero-button {
    margin-top: 2rem;
    padding: 1rem 2rem;
    font-size: 1rem;
    color: var(--text);
    background-color: var(--primary);
    border: none;
    border-radius: 8px;
    cursor: pointer;
    transition: background-color 0.3s, transform 0.3s;
    opacity: 0;
    animation: fadeIn 2s forwards, slideInFromBottom 1.5s forwards;
}

.hero-button:hover {
    background-color: var(--accent);
    transform: scale(1.1);
    box-shadow: 0 6px 12px var(--shadow);
}

@keyframes fadeIn {
    to {
        opacity: 1;
    }
}

@keyframes slideInFromTop {
    from {
        transform: translateY(-50px);
    }
    to {
        transform: translateY(0);
    }
}

@keyframes slideInFromBottom {
    from {
        transform: translateY(50px);
    }
    to {
        transform: translateY(0);
    }
}

.certificate {
    border-radius: 1rem;
    margin-bottom: 1.5rem;
    color: var(--text);
    transition: transform 0.5s ease, box-shadow 0.5s ease; /* Transition properties for scaling and shadow */
    width: 30%;
    z-index: 1000;
    cursor: pointer;
}

.certificate.open {
    transform: scale(3); /* This scales up the certificate */
    box-shadow: 0 12px 24px var(--shadow); /* This adds a shadow effect */
    transition: transform 0.5s ease, box-shadow 0.5s ease; /* Transition properties for scaling and shadow */
}

/* Container for the certificate */
.certificate-container {
    display: flex;
    justify-content: left;
    align-items: left;
    position: relative;
    transition: transform 0.5s ease, box-shadow 0.5s ease, width 0.5s ease, height 0.5s ease, background 0.5s ease; /* Transition properties for container */
    overflow: visible; /* Ensure content doesn't overflow */
}

.certificate-container.open {
    display: flex;
    justify-content: center;
    align-items: center;
    position: fixed;
    top: 0;
    left: 0;
    width: 100vw;
    height: 100vh;
    background: rgba(0, 0, 0, 0.6);
    transform: scale(1); /* This should ensure that the container is not scaled */
    opacity: 1; /* Ensure the container is fully visible */
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
}

.show-more {
    cursor: pointer;
    overflow: hidden;
}

.show-more:hover {
    transform: scale(1.1);
    box-shadow: 0 6px 12px var(--shadow);
}

.show-more::before {
 content: "";
 position: absolute;
 left: 0;
 top: 0;
 width: 100%;
 height: 100%;
 background-color: var(--secondary);
 transform: translateX(-100%);
 transition: all .3s;
 z-index: -1;
}

.show-more:hover::before {
 transform: translateX(0);
}

.projects .project {
    background: var(--accent);
    padding: 1.5rem;
    border-radius: 8px;
    margin-bottom: 1.5rem;
    color: var(--text);
    transition: transform 0.3s, box-shadow 0.3s;
}

.projects .project h3 {
    margin: 0;
    font-size: 1.75rem;
    color: var(--text);
}

.projects .project p {
    margin: 0.75rem 0 0;
}

.github-link {
    display: inline-block;
    margin-top: 0.5rem;
    color: var(--primary);
    text-decoration: none;
    font-weight: bold;
}

.github-icon {
    width: 30px;
    height: 30px;
    fill: #333;
    transition: fill 0.3s ease;
}

.github-link:hover .github-icon {
    fill: #00FF75;
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
    .certificate {
    width: 100%;
}

.certificate.open {
    transform: scale(1); /* This scales up the certificate */
    box-shadow: 0 12px 24px var(--shadow); /* This adds a shadow effect */
    transition: transform 0.5s ease, box-shadow 0.5s ease; /* Transition properties for scaling and shadow */
}
}
</style>
