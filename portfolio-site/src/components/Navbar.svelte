<script>
    let isMenuOpen = false;

    function toggleMenu() {
        isMenuOpen = !isMenuOpen;
    }
</script>

<style>
    .navbar {
        display: flex;
        align-items: center;
        justify-content: space-between;
        padding: 0.6rem;
        background-color: var(--accent);
        position: fixed;
        top: 0;
        left: 0;
        width: 100%;
        box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
        z-index: 1000;
        color: var(--text);
    }

    .logo {
        width: 50px; /* also controls height of navbar */
        height: auto;
    }

    .pages {
        display: flex;
        gap: 5rem;
        margin-right: calc(50% - 10rem);
    }

    .page {
        position: relative;
        cursor: pointer;
        color: var(--text);
    }

    .page:hover {
        color: var(--secondary);
    }

    .page::after {
        content: "";
        position: absolute;
        bottom: -2px;
        left: 0;
        width: 100%;
        height: 2px;
        background-color: var(--secondary);
        transform: scaleX(0);
        transition: transform 0.3s;
    }

    .page:hover::after {
        transform: scaleX(1);
    }

    .hamburger {
        cursor: pointer;
        display: none;
        margin-right: 2rem;
        background-color: rgba(0, 0, 0, 0);
        border: none;
    }

    .hamburger input {
        display: none;
    }

    .hamburger svg {
        height: 3em;
        transition: transform 400ms cubic-bezier(0.4, 0, 0.2, 1);
    }

    .line {
        fill: none;
        stroke: white;
        stroke-linecap: round;
        stroke-linejoin: round;
        stroke-width: 3;
        transition: stroke-dasharray 400ms cubic-bezier(0.4, 0, 0.2, 1),
                    stroke-dashoffset 400ms cubic-bezier(0.4, 0, 0.2, 1);
    }

    .line-top-bottom {
        stroke-dasharray: 12 63;
    }

    .hamburger input:checked + svg {
        transform: rotate(-45deg);
    }

    .hamburger input:checked + svg .line-top-bottom {
        stroke-dasharray: 20 300;
        stroke-dashoffset: -32.42;
    }

    .menu {
        position: absolute;
        top: 100%;
        left: calc(-100% - 2rem); /* Start off-screen */
        width: calc(100% - 2rem);
        padding: 1rem;
        background-color: var(--accent);
        box-shadow: 0 2px 4px rgba(0, 0, 0, 0.3);
        transition: left 0.3s ease-in-out;
        align-content: center;
        justify-content: center;
    }

    .menu.open {
        left: 0%; /* Slide in from the left */
    }

    .menu .page {
        display: block;
        padding: 0.5rem 0.5rem;
        color: var(--text);
        align-content: center;
        justify-content: center;
        text-align: center;
    }

    @media (max-width: 853px) {
        .pages {
            display: none;
        }

        .hamburger {
            display: flex;
        }
    }
</style>

<div class="navbar">
    <img src="src/assets/logo.svg" alt="Logo" class="logo">
    <div class="pages">
        <div class="page">Page 1</div>
        <div class="page">Page 2</div>
        <div class="page">Page 3</div>
        <div class="page">Page 4</div>
    </div>
    <button class="hamburger" on:click={toggleMenu}>
        <input type="checkbox" bind:checked={isMenuOpen}>
        <svg viewBox="0 0 32 32">
            <path class="line line-top-bottom" d="M27 10 13 10C10.8 10 9 8.2 9 6 9 3.5 10.8 2 13 2 15.2 2 17 3.8 17 6L17 26C17 28.2 18.8 30 21 30 23.2 30 25 28.2 25 26 25 23.8 23.2 22 21 22L7 22"></path>
            <path class="line" d="M7 16 27 16"></path>
        </svg>
    </button>
    <div class="menu {isMenuOpen ? 'open' : ''}">
        <div class="page">Page 1</div>
        <div class="page">Page 2</div>
        <div class="page">Page 3</div>
        <div class="page">Page 4</div>
    </div>
</div>
