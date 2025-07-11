<script>
    import { onMount } from 'svelte';
    import { fly } from 'svelte/transition';

    let accepted = false;
    let visible = false;

    onMount(() => {
        const cookieAccepted = localStorage.getItem('cookieAccepted');
        if (!cookieAccepted) {
            visible = true;
        }
    });

    function acceptCookies() {
        localStorage.setItem('cookieAccepted', 'true');
        visible = false;
    }
</script>

{#if visible}
    <div class="cookie-notice" in:fly={{y: 20, delay: 1000}} out:fly={{y: 20, delay: 0}}>
        <p>
            <a href="/integritetspolicy">Vi använder cookies</a> för att göra din upplevelse bättre. Dom hjälper oss förbättra sidan. Är det okej för dig?
        </p>
        <div class="button-container d-flex gap-1 align-center">
            <a class="button tertiary small" href="https://google.se">Nej tack!</a>
            <button class="primary small" on:click={acceptCookies}>Jajamän!</button>
        </div>
    </div>
{/if}

<style lang="scss">
    .cookie-notice {
        position: fixed;
        bottom: 1rem;
        left: 1rem;
        right: 1rem;
        background: var(--color-bg-dark);
        color: #fff;
        padding: 1rem;
        display: flex;
        justify-content: space-between;
        align-items: center;
        z-index: 1000;
        font-size: 0.9rem;
        width: calc(100% - 2rem);
        border-radius: 0.5rem;

        @media (max-width: 768px) {
            flex-direction: column;
            align-items: flex-start;
            gap: 1rem;
        }
    }

    .cookie-notice p {
        margin: 0;
        // max-width: 37.5rem;
        color: white;
    }

    .cookie-notice button:hover {
        background: #eaeaea;
    }
</style>