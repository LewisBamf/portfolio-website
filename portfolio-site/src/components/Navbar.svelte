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
        padding: 1rem;
        background-color: var(--primary);
        position: fixed;
        top: 0;
        left: 0;
        width: 100%;
        box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
        z-index: 1000;
        color: var(--text);
    }

    .logo {
        width: 60px;
        height: auto;
    }

    .pages {
        display: flex;
        gap: 1rem;
        margin-right: 2rem;
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
        display: none;
        cursor: pointer;
        background: none;
        border: none;
        color: var(--text);
        flex-direction: column;
        justify-content: space-between;
        height: 20px;
        margin-right: 2rem;
    }

    .hamburger div {
        width: 25px;
        height: 3px;
        background-color: var(--background);
        transition: all 0.3s;
    }

    .hamburger.open div:nth-child(1) {
        transform: rotate(45deg) translateY(7px);
    }

    .hamburger.open div:nth-child(2) {
        opacity: 0;
    }

    .hamburger.open div:nth-child(3) {
        transform: rotate(-45deg) translateY(-7px);
    }

    .menu {
        display: none;
    }

    @media (max-width: 853px) {
        .pages {
            display: none;
        }

        .hamburger {
            display: flex;
        }

        .menu {
            display: none;
            position: absolute;
            top: 100%;
            left: 0;
            width: 100%;
            padding: 1rem;
            background-color: var(--primary);
            box-shadow: 0 2px 4px rgba(0, 0, 0, 0.3);
        }

        .menu.open {
            display: block;
        }

        .menu .page {
            display: block;
            padding: 0.5rem 0;
            color: var(--background);
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
    <button class="hamburger {isMenuOpen ? 'open' : ''}" on:click={toggleMenu} aria-label="Toggle Menu">
        <div></div>
        <div></div>
        <div></div>
    </button>
    <div class="menu {isMenuOpen ? 'open' : ''}">
        <div class="page">Page 1</div>
        <div class="page">Page 2</div>
        <div class="page">Page 3</div>
        <div class="page">Page 4</div>
    </div>
</div>
