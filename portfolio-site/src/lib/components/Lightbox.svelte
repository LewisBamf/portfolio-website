<script>
    export let imageSrc = '';
    export let isOpen = false;
    
    function closeLightbox() {
        isOpen = false;
    }
</script>

{#if isOpen}
<!-- svelte-ignore a11y-click-events-have-key-events -->
<!-- svelte-ignore a11y-no-static-element-interactions -->
<div class="lightbox" on:click={closeLightbox}>
    <div class="lightbox-content">
        <img src={imageSrc} alt="Certificate" />
    </div>
</div>
{/if}

<style>
.lightbox {
    position: fixed;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    background: rgba(0, 0, 0, 0.8);
    display: flex;
    justify-content: center;
    align-items: center;
    z-index: 1000;
}

.lightbox-content {
    position: relative;
}

.lightbox-content img {
    max-width: 90%;
    max-height: 90%;
    border: 2px solid white;
    border-radius: 8px;
}
</style>
