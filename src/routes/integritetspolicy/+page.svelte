<script>
    import Footer from "$lib/components/Footer.svelte";
</script>

<main class="px-3 py-4">
    <div class="header">
        <img src="/images/hilja-logo-horizontal.svg" width="300"/>
    </div>
    <h2 class="pt-xs-5 font-bold text-center">Integritetspolicy</h2>
    <p class="mb-1 text-center">Senast uppdaterad: 11 juli 2025</p>
    <a class="button primary mb-2" style="width: fit-content; text-align: center; margin-left: auto; margin-right: auto;" href="/">Tillbaka till startsidan</a>
   <p class="mb-5 text-center">Hilja Logistics värnar om din personliga integritet och följer dataskyddsförordningen (GDPR). <br> Den här policyn förklarar hur vi samlar in, använder och skyddar dina personuppgifter.</p>
   <section class="mb-4 mt-2">
      <h3 class="text-2xl font-semibold mb-1">1. Vem är ansvarig för dina personuppgifter?</h3>
      <p>Hilja Logistics är personuppgiftsansvarig för behandlingen av dina uppgifter.<br><strong>Kontakt:</strong><br>Hilja Logistics<br>E-post: <a href="mailto:hilja@hiljalogistics.se">hilja@hiljalogistics.se</a><br>Telefon: <a href="tel:+46705284448">+46 705 28 44 48</a></p>
   </section>
   <section class="mb-4">
      <h3 class="text-2xl font-semibold mb-1">2. Vilka uppgifter samlar vi in – och varför?</h3>
      <p class="mb-1">När du använder vår webbplats eller kontaktar oss, samlar vi in:</p>
      <ul class="mb-1">
         <li>Namn</li>
         <li>Företagsnamn</li>
         <li>E-postadress</li>
         <li>Telefonnummer</li>
      </ul>
      <p><strong>Syfte:</strong> Vi använder dessa uppgifter för att kunna kontakta dig i ärenden som rör våra tjänster och för att besvara dina förfrågningar.</p>
   </section>
   <section class="mb-4">
      <h3 class="text-2xl font-semibold mb-1">3. Använder vi cookies eller analysverktyg?</h3>
      <p class="mb-1">Ja. Vi använder <strong>Google Analytics</strong> för att förstå hur besökare använder vår webbplats.</p>
      <p class="mb-1"><strong>Vad innebär det?</strong> Google Analytics samlar in anonymiserad data som t.ex. IP-adress, enhetstyp, webbläsare och besökstid.</p>
      <p class="mb-1"><strong>Rättslig grund:</strong> Berättigat intresse (artikel 6.1 f GDPR).</p>
      <p>Du kan neka cookies via din webbläsares inställningar eller via vårt cookie-samtyckesverktyg (om du har ett implementerat).</p>
   </section>
   <section class="mb-4">
      <h3 class="text-2xl font-semibold mb-1">4. Hur länge sparar vi dina uppgifter?</h3>
      <p>Vi sparar dina uppgifter så länge som det är nödvändigt för att uppfylla syftet – t.ex. så länge vi har en aktiv dialog – men aldrig längre än 12 månader utan kontakt, om inte annat krävs enligt lag.</p>
   </section>
   <section class="mb-4">
      <h3 class="text-2xl font-semibold mb-1">5. Delar vi dina uppgifter med andra?</h3>
      <p>Nej, vi säljer aldrig dina uppgifter. Vi kan däremot använda externa tjänsteleverantörer (t.ex. e-posttjänster eller CRM-system) som hanterar data åt oss under strikt dataskyddsavtal (biträdesavtal).</p>
   </section>
   <section class="mb-4">
      <h3 class="text-2xl font-semibold mb-1">6. Dina rättigheter enligt GDPR</h3>
      <p class="mb-1">Du har rätt att:</p>
      <ul class="mb-1">
         <li>Få tillgång till dina uppgifter (registerutdrag)</li>
         <li>Rätta felaktiga uppgifter</li>
         <li>Bli raderad (“rätten att bli bortglömd”)</li>
         <li>Invända mot behandling</li>
         <li>Begära dataportabilitet</li>
         <li>Återkalla samtycke när som helst (om tillämpligt)</li>
      </ul>
      <p>
         Vill du utöva någon av dina rättigheter? Kontakta oss på<!-- --> <a href="mailto:hilja@hiljalogistics.se">hilja@hiljalogistics.se</a>.
      </p>
   </section>
   <section class="mb-4">
      <h3 class="text-2xl font-semibold mb-1">7. Hur skyddar vi dina uppgifter?</h3>
      <p>Vi använder tekniska och organisatoriska säkerhetsåtgärder för att skydda dina personuppgifter mot obehörig åtkomst, förlust eller spridning.</p>
   </section>
   <section class="mb-4">
      <h3 class="text-2xl font-semibold mb-1">8. Klagomål?</h3>
      <p>
         Om du anser att vi behandlar dina uppgifter felaktigt, har du rätt att lämna in ett klagomål till<!-- --> <a href="https://www.imy.se" target="_blank" rel="noopener noreferrer">Integritetsskyddsmyndigheten (IMY)</a>.
      </p>
   </section>
</main>

<Footer/>

<style>
    .header {
        display: flex;
        justify-content: center;
        width: 100%;
        margin-bottom: 2rem;
        
        @media (max-width: 768px) {
            margin-top: 4rem;
            margin-bottom: 0;
        }

        img {
            width: 18.75rem;
        }
    }
    section {
        max-width: 1000px;
        margin-left: auto;
        margin-right: auto;
    }
</style>
