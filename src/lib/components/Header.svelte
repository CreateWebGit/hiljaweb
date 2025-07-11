<script>
    import { onMount, onDestroy } from "svelte";
    
    let header;
    let observer;
    const sectionIds = ['intro', 'om', 'process', 'erfarenhet', 'kontakt'];

    let mobileSlideMenuActive = false;

    onMount(() => {
        let prevScrollpos = 0;
        header = document.getElementById("hl-header");

        function handleHeaderScroll() {
            const currentScrollPos = window.scrollY;

            if (currentScrollPos === 0) {
                header.classList.add('at-top')
            }

            if (currentScrollPos > 0) {
                header.classList.remove('at-top')
            }

            if (prevScrollpos <= currentScrollPos ){
                header.classList.add("scrolled");
            } else {  
                header.classList.remove('scrolled');
            }

            prevScrollpos = currentScrollPos;
        }

        window.addEventListener('scroll', handleHeaderScroll)

        const options = {
            root: null,
            rootMargin: '0px',
            threshold: 0.6 // triggers when 60% of a section is visible
        };

        observer = new IntersectionObserver(handleIntersect, options);

        sectionIds.forEach(id => {
            const section = document.getElementById(id);
            if (section) observer.observe(section);
        });

        return () => observer.disconnect(); // Clean up on destroy
    })

    function handleIntersect(entries) {
        entries.forEach(entry => {
            const id = entry.target.id;
            const desktopLink = document.querySelector(`.desktop-nav a[href="#${id}"]`);
            const mobileLink = document.querySelector(`.mobile-nav a[href="#${id}"]`);

            if (entry.isIntersecting) {
                document.querySelectorAll('nav a').forEach(a => a.classList.remove('active'));
                desktopLink.classList.add('active');
                mobileLink.classList.add('active');
            }
        });
    }

    function handleToggleSlideMenu() {
        console.log('shiet')
        mobileSlideMenuActive = !mobileSlideMenuActive;

        if (mobileSlideMenuActive) {
            header.classList.remove('at-top')
            document.querySelector('html').style.overflow = 'hidden';
        } else if (!mobileSlideMenuActive && window.scrollY == 0) {
            header.classList.add('at-top')
        }

        if (!mobileSlideMenuActive) {
            document.querySelector('html').removeAttribute('style')
        }
    }
</script>


<header id="hl-header" class="at-top">
    <div class="logo-container justify-start">
        <img src="/images/hilja-logo-horizontal.svg" width="164" height="35" alt="hilja logistics logo">
    </div>
    <div class="nav-container justify-center">
        <nav class="desktop-nav">
            <a class="active" href="#intro">Intro</a>
            <a href="#om">Om</a>
            <a href="#process">Vår process</a>
            <a href="#erfarenhet">Vår Erfarenhet</a>
            <a href="#kontakt">Kontakt</a>
        </nav>
    </div>
    <div class="button-container justify-end">
        <a class="button primary small" href="#kontakt">Kontakta oss</a>
        <button on:click={() => handleToggleSlideMenu()} class="hamburger hamburger--spin {mobileSlideMenuActive ? 'is-active' : ''} hide-desktop" aria-label="button to toggle slide menu">
        <span class="hamburger-box">
            <span class="hamburger-inner"></span>
        </span>
        </button>
    </div>
</header>

<div class="mobile-slide-menu {mobileSlideMenuActive ? 'open' : ''}">
    <div class="content">
        <div class="top-container">
            <nav class="mobile-nav">
                <a on:click={() => handleToggleSlideMenu()} href="#intro">Intro</a>
                <a href="#om" on:click={() => handleToggleSlideMenu()}>Om oss</a>
                <a href="#process" on:click={() => handleToggleSlideMenu()}>Vår process</a>
                <a href="#erfarenhet" on:click={() => handleToggleSlideMenu()}>Vår erfarenhet</a>
                <a href="#kontakt" on:click={() => handleToggleSlideMenu()}>Kontakt</a>
            </nav>

            <div class="button-container">
                <a href="#kontakt" on:click={() => handleToggleSlideMenu()} class="button primary mx-auto">Kontakta oss idag</a>
            </div>
        </div>
    </div>
</div>