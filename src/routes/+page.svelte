<script>
    import SectionHero from "$lib/components/SectionHero.svelte";
    import SectionVanlig from "$lib/components/SectionVanlig.svelte";
    import SectionKan from "$lib/components/SectionKan.svelte";
    import SectionHelp from "$lib/components/SectionHelp.svelte";
    import SectionErfarenhet from "$lib/components/SectionErfarenhet.svelte";
    import SectionKontakt from "$lib/components/SectionKontakt.svelte";

    import Header from "$lib/components/Header.svelte";
    import Footer from "$lib/components/Footer.svelte";
    import CookieNotice from "$lib/components/CookieNotice.svelte";
</script>

<svelte:head>
    <title>Hilja Logistics – Skräddarsydd logistik utan krångel</title>
    <meta name="description" content="Vi hjälper företag hitta rätt logistiklösning, från frakt och lager till hela supply chain. Ingen försäljning. Bara gratis rådgivning tills du är redo." />
    <meta name="keywords" content="logistik, logistiklösningar, 3PL, lagerlösning, företagslogistik, skräddarsydd logistik, supply chain, transportlösningar, frakt, tredjepartslogistik, fraktpartner, logistikpartner, logistikrådgivning, fraktföretag, kostnadsfri logistikrådgivning, smart logistik, fraktlösning, lager och frakt, företagsfrakt, logistiknätverk, Hilja Logistics" />
    <meta name="viewport" content="width=device-width, initial-scale=1" />
    <meta charset="UTF-8" />

    <meta property="og:title" content="Hilja Logistics – Skräddarsydd logistik utan krångel" />
    <meta property="og:description" content="Nästan 150 års erfarenhet. Vi hittar rätt lösning för dig, inte tvärtom." />
    <meta property="og:image" content="https://hiljalogistics.se/og-image.jpg" />
    <meta property="og:url" content="https://hiljalogistics.se" />
    <meta property="og:type" content="website" />

    <meta name="twitter:card" content="summary_large_image" />
    <meta name="twitter:title" content="Hilja Logistics – Skräddarsydd logistik utan krångel" />
    <meta name="twitter:description" content="Vi hjälper företag hitta logistiklösningar utan kostnad. Kontakta oss för rådgivning." />
    <meta name="twitter:image" content="https://hiljalogistics.se/og-image.jpg" />
</svelte:head>

<main>
    <Header/>
    <SectionHero/>
    <SectionVanlig/>
    <SectionKan/>
    <SectionHelp/>
    <SectionErfarenhet/>
    <SectionKontakt/>
    <Footer/>
    <CookieNotice/>
</main>