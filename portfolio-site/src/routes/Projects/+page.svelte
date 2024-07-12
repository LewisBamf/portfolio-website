<script>
    import Navbar from '$lib/components/Navbar.svelte';
    import Footer from '$lib/components/Footer.svelte';
    import '../../global.css';

    // Example projects - replace these with your actual projects
    const projects = [
        {
            title: 'Verlet Physics Pendulum',
            description: 'A simple pendulum simulation using Verlet integration to model realistic physics in 2D space.',
            github: 'https://github.com/LewisBamf/pendulum-project'
        },
        {
            title: 'Verlet Physics Simulator',
            description: 'A physics simulator that uses Verlet integration to model rigid body dynamics and collisions in 2D space.',
            github: 'https://github.com/LewisBamf/Verlet-Physics-sim'
        },
        {
            title: 'Using tensorflow to solve the MNIST database',
            description: 'A simple neural network using TensorFlow to classify handwritten digits from the MNIST database.',
            github: 'https://github.com/LewisBamf/tensorflow-test-Greyscale-Handdrawn-Images'
        },
        {
            title: 'Personal Portfolio',
            description: 'My own portfolio website built with Svelte to showcase my skills and projects.',
            github: 'https://github.com/LewisBamf/portfolio-website'
        },
        {
            title: 'Euclidean Physics Simulation',
            description: 'A physics simulation using Euclidean geometry to model rigid body dynamics and collisions in 2D space.',
            github: 'https://github.com/LewisBamf/Physics-init'
        },
    ];
</script>

<main>

    <section class="hero">
        <div class="container">
            <h1>My Projects</h1>
            <p>Explore my projects to see what I’ve been working on lately. Each project includes a brief description and a link to the GitHub repository.</p>
        </div>
    </section>

    <section class="timeline">
        <div class="timeline-node"></div>
        {#each projects as { title, description, github }, i}
            <div class="event">
                <div class="event-content">
                    <h2>{title}</h2>
                    <p>{description}</p>
                    <a href={github} target="_blank" rel="noopener noreferrer" class="github-link">
                        <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" fill="currentColor" class="github-icon">
                            <path d="M12 0C5.372 0 0 5.373 0 12c0 5.308 3.438 9.808 8.207 11.39.6.111.82-.26.82-.578 0-.286-.01-1.046-.015-2.057-3.338.725-4.04-1.606-4.04-1.606-.545-1.384-1.333-1.751-1.333-1.751-1.088-.743.083-.728.083-.728 1.205.084 1.838 1.236 1.838 1.236 1.07 1.836 2.809 1.305 3.493.998.107-.775.418-1.305.763-1.605-2.665-.303-5.466-1.332-5.466-5.928 0-1.31.469-2.381 1.24-3.222-.125-.303-.538-1.52.115-3.175 0 0 1.01-.323 3.3 1.228.957-.266 1.981-.399 3.001-.404 1.02.005 2.046.138 3.002.404 2.291-1.551 3.297-1.228 3.297-1.228.653 1.655.241 2.872.116 3.175.77.841 1.237 1.912 1.237 3.222 0 4.605-2.804 5.622-5.473 5.922.43.371.815 1.104.815 2.224 0 1.606-.015 2.913-.015 3.303 0 .319.22.694.825.578A12.026 12.026 0 0024 12c0-6.627-5.373-12-12-12z"/>
                        </svg>
                    </a>
                </div>
            </div>
        {/each}
    </section>

    <Navbar />
    <Footer />
</main>

<style>
/* Remove blue underlines on links */
a {
    text-decoration: none; /* Remove underline */
    color: inherit; /* Make link color inherit from parent */
}

/* Style for the GitHub link */
.github-link {
    display: inline-block;
    color: #333;
    margin-top: 1rem;
}

.github-icon {
    width: 30px;
    height: 30px;
    fill: #333;
    transition: fill 0.3s ease;
}

.github-link:hover .github-icon {
    fill: #00FF75; /* Change icon color on hover */
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
    font-family: var(--text);
    font-size: 3rem;
    margin: 0 0 1rem 0;
}

.hero p {
    font-size: 1.25rem;
}

.timeline {
    position: relative;
    max-width: 900px; /* Same width as container */
    margin: 0 auto;
    padding: 2rem;
}

/* Add a single node at the center of the timeline */
.timeline-node {
    position: absolute;
    width: 30px; /* Node size */
    height: 30px;
    background: #00FF75; /* Glowing color */
    border-radius: 50%;
    border: 4px solid var(--background); /* Border color */
    box-shadow: 0px 0px 10px 1px rgba(0, 255, 117, 0.30); /* Glowing effect */
    left: 50%;
    transform: translateX(-50%);
    top: 0;
    z-index: 1; /* Ensure the node is above the line */
}

/* Make the timeline line thicker */
.timeline::before {
    content: '';
    position: absolute;
    top: 20px; /* Start line below the node */
    bottom: 0;
    width: 4px; /* Line thickness */
    background: linear-gradient(to bottom, rgba(0, 255, 117, 0.5), rgba(0, 255, 117, 0)); /* Glowing effect */
    left: 50%;
    transform: translateX(-50%);
}

/* Add a connecting line to the events */
.timeline .event::before {
    content: '';
    position: absolute;
    width: 2px;
    background: #00FF75; /* Matching color for the line */
    top: 20px; /* Position the line from the top of the node */
    bottom: -20px; /* Extend the line below the event */
    left: 50%;
    transform: translateX(-50%);
    z-index: 0; /* Ensure the line is behind the content */
}

/* Position nodes */
.timeline .event {
    position: relative;
    margin-bottom: 4rem;
    padding: 1rem; /* Space for the nodes */
}

/* Move odd events to the right */
.timeline .event:nth-child(odd) {
    margin-left: 50%; /* Adjust to position on the right side */
    text-align: left; /* Align text to the left */
}

/* Move even events to the left */
.timeline .event:nth-child(even) {
    margin-right: 50%; /* Adjust to position on the left side */
    text-align: right; /* Align text to the right */
}

/* Style for the content of events */
.timeline .event .event-content {
    background: var(--background);
    padding: 1rem;
    border-radius: 10px;
    box-shadow: 0px 0px 10px 1px rgba(0, 255, 117, 0.30);
    position: relative;
}

/* Ensure the node is on top of the line */
.timeline .event::before {
    content: '';
    position: absolute;
    width: 20px; /* Increased size for better visibility */
    height: 20px;
    background: #00FF75; /* Glowing color */
    border-radius: 50%;
    border: 4px solid var(--background); /* Add border */
    box-shadow: 0px 0px 10px 1px rgba(0, 255, 117, 0.30); /* Glowing effect */
    left: 50%;
    transform: translateX(-50%); /* Center on the line */
    z-index: 1; /* Bring the node above the line */
}

/* Position nodes */
.timeline .event:nth-child(odd)::before {
    top: 50%;
    left: 0%;
    margin-top: -10px; /* Center the node */
}

.timeline .event:nth-child(even)::before {
    top: 50%;
    left: 100%;
    margin-top: -10px; /* Center the node */
}

@media (max-width: 600px) {
    .timeline {
        padding: 1rem;
    }
    .timeline .event:nth-child(odd),
    .timeline .event:nth-child(even) {
        margin-left: 0;
        margin-right: 0;
        text-align: center; /* Center text on small screens */
    }
    
    .timeline .event::before {
        left: 1rem; /* Adjust for mobile */
    }

    .timeline .event:nth-child(odd)::before {
    display: none; /* Hide nodes on odd events */
    }

    .timeline .event:nth-child(even)::before {
    display: none; /* Hide nodes on odd events */
    }

    .github-icon {
    width: 30px;
    height: 30px;
    fill: #00FF75; /* Change icon color on hover */
    transition: fill 0.3s ease;
    }
}
</style>
