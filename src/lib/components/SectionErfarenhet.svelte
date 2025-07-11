<script>
    let logoImages = [
        {
            link: '',
            image: '/images/dhl_logo.svg',
            class: 'dhl'
        },
        {
            link: '',
            image: '/images/dsv_logo.svg',
            class: 'dsv'
        },
        {
            link: '',
            image: '/images/postnord_logo.svg',
            class: 'postnord'
        },
        {
            link: '',
            image: '/images/bring_logo.svg',
            class: 'bring'
        },
        {
            link: '',
            image: '/images/fraktjakt_logo.svg',
            class: 'fraktjakt'
        },
        {
            link: '',
            image: '/images/mantell-logga-vit.png',
            class: 'mantell'
        },
        {
            link: '',
            image: '/images/createweb_logo.svg',
            class: 'cw'
        }
    ]
</script>

<section id="erfarenhet" class="hl-section--erfarenhet cw-grid section-full-width section-y-padding-xl">
    <div class="cw-col-4 cw-col-xs-12">
        <h2 class="text-full-white">Över <span class="text-accent">100 års</span> erfarenhet av logistik</h2>
        <p class="text-white mt-1">Vi på Hilja Logistics har tillsammans jobbat med logistik i över ett sekel. På alla nivåer. Vi förstår både detaljerna och helheten.</p>
        <a class="button primary width-fit mt-3 hide-mobile" href="#kontakt">Kontakta oss idag</a>
    </div>
    <div class="cw-col-1 hide-mobile"></div>
    <div class="cw-col-7 cw-col-xs-12">
        <h3>Med ett brett nätverk av beprövade partners, som Fraktjakt och Mantell, hjälper vi dig hitta rätt logistiklösning snabbt och smidigt. <span class="text-white">Du får direktkontakt utan mellanhänder, och vår erfarenhet säkerställer att du slipper onödiga misstag.</span></h3>
        <div class="number-container mt-4 hide-mobile">
            <div class="number">
                <h1>100+</h1>
                <p class="text-white">år av erfarenhet</p>
            </div>
            <div class="number">
                <h1>100%</h1>
                <p class="text-white">nöjda kunder</p>
            </div>
            <div class="number">
                <h1>10+</h1>
                <p class="text-white">samarbetspartners</p>
            </div>
        </div>
    </div>
    <div class="cw-col-12 cw-col-xs-12">
        <div class="logo-container">
            {#each logoImages as logo}
                <img src={logo.image} class={logo.class} alt="logo for"/>
            {/each}
        </div>
        <a class="button primary width-fit mt-5 hide-desktop mx-auto" href="#kontakt">Kontakta oss idag</a>
    </div>
</section>