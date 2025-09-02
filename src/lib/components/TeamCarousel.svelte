<script>
    import { onMount } from 'svelte';
    import { fade, fly } from 'svelte/transition'

    let team = $state([
        {
            img: '/images/hilja.JPG',
            name: 'Hilja Heikkinen',
            position: 'Logistikkonsult',
            description: '"Har arbetat med alla transportmedel, fraktat import/export över hela världen. Kliat mig i huvudet över alla tullregler, farligt gods och tillfälliga utmaningar som stormat. Ser logistikarbetet som framtidens bana och hinder att möta med spänning. Befinner mig i skogen utanför Borås. Där kan jag stressa av i min bastu."',
            contactDetails: {
                email: 'hilja@hiljalogistics.se',
                phone: '+46 705 28 44 48',
                linkedInLink: 'https://www.linkedin.com/in/hilja-heikkinen-a969a312b/'
            }
        },
        {
            img: '/images/andreas.jpeg',
            name: 'Andreas Hansson',
            position: 'Logistikkonsult',
            description: '"Som en nyfiken och resvan logistikkonsult brinner jag för att kombinera praktisk erfarenhet med nya lärdomar. Min passion är att hjälpa företag att optimera sina flöden och sänka kostnader. Jag tror på att ständig utveckling och insikter från olika håll – precis som på en resa – leder till de mest innovativa och effektiva lösningarna för din verksamhet."',
            contactDetails: {
                email: 'andreas@hiljalogistics.se',
                linkedInLink: 'https://www.linkedin.com/in/andreashansson1/'
            }
        },
        {
            img: '/images/henrik.jpeg',
            name: 'Henrik Johansson',
            position: 'Logistikkonsult',
            description: '"Har jobbat med logistik och vägtransporter över hela Europa. Sett asfalten rulla undan och styrt många lastbilar längs vägarna. Både som speditör, åkare och förare. Med mer än 40 års erfarenhet är det fortfarande spänning i vardagen över att se logistiken förändras över hela världen. Befinner mig i Malmös hetsiga puls över livet med det inre lugnets motor."',
            contactDetails: {
                email: 'henrik@hiljalogistics.se',
                linkedInLink: 'https://www.linkedin.com/in/henrik-johansson-helsingborg-attityder-transport/'
            }
        }
    ]);

    let carouselTimer = $state();
    let activeSlide = $state(0)
    let prevSlide = $state(0);

    const direction = $derived(() => {
        return activeSlide > prevSlide ? 1 : -1;
    });

    const goToSlide = (i) => {
        prevSlide = activeSlide
        activeSlide = i
    }

    const goToNextSlide = () => {
        prevSlide = activeSlide

        if (activeSlide === team.length - 1) {
            activeSlide = 0
        } else {
            activeSlide++;
        }
    }

    const goToPreviousSlide = () => {
        prevSlide = activeSlide

        if (activeSlide != 0) {
            activeSlide--;
        }
    }

    const extractLinkedInHandler = (url) => {
        const match = url.match(/linkedin\.com\/in\/([^/]+)/i);
        return match ? `@${match[1]}` : null;
    }

    onMount(() => {
        carouselTimer = setInterval(goToNextSlide, 20000);
    })
</script>
<!-- in:fly={{ x: direction() * 100, duration: 500, delay: 300 }} out:fly={{y: 50, duration: 500}} -->
<div class="team-carousel-wrapper">
    <div class="team-carousel-container">
        {#each team as member, i (member.name)}
            {#if activeSlide === i}
                <div class="team-carousel-item" in:fly={{ x: direction() * 100, duration: 500, delay: 300 }} out:fly={{y: 50, duration: 500}}>
                    <div class="team-image-container">
                        <img src={member.img} alt="test"/>
                    </div>
                    <div class="team-info-container">
                        <div>
                            <h2 class="team-name text-full-white">{member.name}</h2>
                            <!-- <h3 class="font-w-bold team-position text-full-white">{member.position}</h3> -->
                        </div>
                        <p class="team-description text-white" style="width: 90%">{member.description}</p>
                        <div class="team-contact-details">
                            <ul>
                                <li><a href={`mailto:${member.contactDetails.email}`}>{member.contactDetails.email}</a></li>
                                {#if member.contactDetails.phone}
                                    <li><a href={`tel:${member.contactDetails.phone}`}>{member.contactDetails.phone}</a></li>
                                {/if}
                                <li style="text-transform: lowercase;"><a href={member.contactDetails.linkedInLink} target="_blank">@{member.name.replace(' ', '')}</a></li>
                            </ul>
                        </div>
                    </div>
                </div>
            {/if}
        {/each}
        <div class="team-carousel-thumbnails-container">
            {#each team as member, i (member.name)}
                <div onclick={() => goToSlide(i)} class={`team-carousel-thumbnail ${activeSlide === i ? 'active' : ''}`} role="button" tabindex="0">
                    <img src={member.img}/>
                </div>
            {/each}
        </div>
    </div>
    <div class="indicator-button-container">
        <div class="team-carousel-indicators {carouselTimer != null ? 'animation-on' : ''}">
            {#each team as member, i}
                <div class="indicator {i === activeSlide ? 'active': ''}">
                    <div class="progress"></div>
                </div>
            {/each}
        </div>
        <div class="button-container d-flex gap-1">
            <button onmouseenter={() => (clearInterval(carouselTimer), carouselTimer = null)} class="round left" onclick={goToPreviousSlide}>
                <img src="/icons/caret-right.svg"/>
            </button>
            <button onmouseenter={() => (clearInterval(carouselTimer), carouselTimer = null)} class="round" onclick={goToNextSlide}>
                <img src="/icons/caret-right.svg"/>
            </button>
        </div>
    </div>
</div>