<script>
    import Navbar from '$lib/components/Navbar.svelte';
    import '../global.css';
    import { dev } from '$app/environment';
import { inject } from '@vercel/analytics';
 
inject({ mode: dev ? 'development' : 'production' });
</script>

<Navbar />
<main>
    <slot />
</main>
