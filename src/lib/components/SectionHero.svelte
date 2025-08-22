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
            image: '/images/mantell-logga-vit.webp',
            class: 'mantell'
        },
        {
            link: '',
            image: '/images/createweb_logo.svg',
            class: 'cw'
        }
    ]
</script>

<section id="intro" class="hl-section--hero section-full-width section-y-padding">
    <div class="cw-col-12 cw-col-xs-12 text-center">
        <h1>Vi hittar <span class="text-accent">rätt</span> <br> logistik för dig</h1>
        <p class="mt-1">Vi hjälper dig hitta rätt logistik. Oavsett om det handlar om lager, frakt <br class="hide-mobile"> eller hela supply chain, hjälper vi dig att hitta den rätta vägen.</p>
        <a class="button primary mt-2 width-fit mx-auto" href="#kontakt">Kontakta oss idag</a>
    </div>
    <div class="partners">
    <p class="text-full-white mb-1">VÅRA SAMARBETSPARTNERS</p>

    <div class="marquee">
      <div class="track">
        <div class="group">
          {#each logoImages as logo}
            <div class="partner-card">
              <img class={logo.class} src={logo.image} alt={logo.class} height="auto" />
            </div>
          {/each}
        </div>

        <div class="group">
          {#each logoImages as logo}
            <div class="partner-card">
              <img class={logo.class} src={logo.image} alt={logo.class} height="auto" />
            </div>
          {/each}
        </div>

        <!-- duplicate for seamless loop -->
        <div class="group" aria-hidden="true">
          {#each logoImages as logo}
            <div class="partner-card">
              <img class={logo.class} src={logo.image} alt={logo.class} height="auto" />
            </div>
          {/each}
        </div>
      </div>
    </div>
  </div>
</section>

<style lang="scss">
.partners {
    position: absolute;
    left: 0; right: 0; bottom: 2rem;
    overflow: hidden;
    text-align: center;

    -webkit-mask-image: linear-gradient(to right, transparent, black 10%, black 90%, transparent);
    -webkit-mask-repeat: no-repeat;
    -webkit-mask-size: 100% 100%;
    mask-image: linear-gradient(to right, transparent, black 10%, black 90%, transparent);
    mask-repeat: no-repeat;
    mask-size: 100% 100%;
}

.marquee {
    overflow: hidden;
}

.track {
    display: flex;
    width: max-content;
    animation: marquee 40s linear infinite;
    will-change: transform;
}

.group {
    display: inline-flex;
    flex-shrink: 0;
}

.partner-card {
    background: rgba(255,255,255,0.75);
    height: 4rem;
    width: 12rem;
    display: flex;
    align-items: center;
    justify-content: center;
    border-radius: 0.25rem;
    border: 2px solid rgba(255,255,255,0.50);
    margin-right: 0.5rem;
}

.partner-card img {
    height: 1.40rem;
    filter: invert(1);
    opacity: 0.75;
}
.partner-card img.bring { height: 1.75rem; }
.partner-card img.dhl { height: 1.35rem; }

@keyframes marquee {
    from { transform: translateX(0); }
    to   { transform: translateX(-33.333%); } /* 3 groups → move by exactly one */
}
</style>