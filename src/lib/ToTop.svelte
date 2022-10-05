<script lang="ts">
    const scrollToTop = () => window.scrollTo(0, 0);
    import { fade } from 'svelte/transition';
</script>

<div transition:fade={{delay: 100, duration: 200}} on:click="{scrollToTop}" >
    <svg viewBox="0 0 23 35" xmlns="http://www.w3.org/2000/svg">
        <path d="M12.5765 0.947641C11.9907 0.361854 11.041 0.361854 10.4552 0.947641L0.909267 10.4936C0.323481 11.0794 0.323481 12.0291 0.909267 12.6149C1.49505 13.2007 2.4448 13.2007 3.03059 12.6149L11.5159 4.12962L20.0012 12.6149C20.5869 13.2007 21.5367 13.2007 22.1225 12.6149C22.7083 12.0291 22.7083 11.0794 22.1225 10.4936L12.5765 0.947641ZM13.0159 34.0083L13.0159 2.0083H10.0159L10.0159 34.0083H13.0159Z"/>
    </svg>
</div>

<style>
    div {
        position: fixed;
        bottom: 50%;
        right: 1rem;
        cursor: pointer;
        z-index: 100;
        /* background-color: var(--text-tertiary); */
        border-radius: 50%;
        padding: 0.5rem;
        width: 1.5em;
        height: 1.5em;
        display: grid;
        place-items: center;
        /* box-shadow: 0.15rem 0.15rem 0.2rem var(--text-tertiary); */
    }
    svg {
        height: 1.5em;
        width: 1.5em;
        fill: var(--text-primary);
    }
</style>