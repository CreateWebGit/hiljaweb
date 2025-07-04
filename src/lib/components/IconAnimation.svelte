<script>
    const icons = [
        '/icons/bag.svg',
        '/icons/boat.svg',
        '/icons/box-up-arrow.svg',
        '/icons/box.svg',
        '/icons/container.svg',
        '/icons/plane.svg',
        '/icons/train.svg',
        '/icons/truck.svg',
    ];

    const totalIcons = 15;
    let floatingIcons = [];

    let idCounter = 0;

    function spawnIcon() {
        const icon = {
            id: idCounter++,
            src: icons[Math.floor(Math.random() * icons.length)],
            top: Math.random() * 100,
            duration: 10 + Math.random() * 10,
            key: Math.random() // force a re-render of the icon
        };

        floatingIcons = [...floatingIcons, icon];

        if (floatingIcons.length < totalIcons) {
            const delay = 100 + Math.random() * 400;
            setTimeout(spawnIcon, delay);
        }
    }

    function respawnIcon(id) {
        floatingIcons = floatingIcons.map(icon => {
            if (icon.id === id) {
                return {
                    ...icon,
                    src: icons[Math.floor(Math.random() * icons.length)],
                    top: Math.random() * 100,
                    duration: 20 + Math.random() * 10,
                    key: Math.random()
                };
            }
            return icon;
        });
    }

    spawnIcon();
</script>

<div class="icon-container">
    {#each floatingIcons as icon (icon.key)}
        <img
            src={icon.src}
            class="floating-icon"
            style="top: {icon.top}%; animation-duration: {icon.duration}s"
            alt="icon"
            on:animationend={() => respawnIcon(icon.id)}
        />
    {/each}
</div>

<style lang="scss">
    .icon-container {
        position: fixed;
        bottom: 0;
        z-index: 0;
        opacity: 0.5;
        left: 0;
        width: 100%;
        height: 30rem;
        pointer-events: none;
        overflow: hidden;

        @media (max-width: 768px) {
            display: none;
        }
    }

    .floating-icon {
        position: absolute;
        left: -100px;
        width: 30px;
        height: auto;
        animation-name: floatRight;
        animation-timing-function: linear;
        animation-fill-mode: forwards;
        background: var(--color-bg);
    }

    @keyframes floatRight {
        from {
            transform: translateX(0);
        }
        to {
            transform: translateX(110vw);
        }
    }
</style>