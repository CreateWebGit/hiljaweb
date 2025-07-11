<script>
	import { page } from '$app/state';
</script>

<svelte:head>
    <title>Aj då, något gick fel &mdash; Hilja Logistics</title>
</svelte:head>

<div class="error-container">
    <img src="/images/hilja-logo-horizontal.svg" alt="hl logo"/>
    <div class="error-message-container">
        <h2>Aj då!</h2>
        <h3>Det verkar som att den här <br/> sidan fastnade i tullen.</h3>
        <p>Vi vet var alla paket befinner sig, men <br/> inte den här sidan.</p>
        <a href="/" class="button primary mx-auto">Tillbaka till startsidan</a>
    </div>
</div>

<style lang="scss">
.error-container {
    display: grid;
    place-items: center;
    height: 100dvh;
    width: 100%;
    position: relative;

    img {
        position: absolute;
        top: 2rem;
        left: 0;
        margin: auto;
        right: 0;
    }

    .error-message-container {
        display: flex;
        flex-direction: column;
        text-align: center;
        margin-top: 2rem;

        h2 {
            font-size: 4rem;
            font-weight: 700;
            color: var(--color-accent);
            margin-bottom: 0.75rem;
        }

        h3 {
            margin-bottom: 0.5rem;
        }

        p {
            margin-bottom: 2rem;
        }
    }
}
</style>