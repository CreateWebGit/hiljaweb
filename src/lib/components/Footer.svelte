<footer>
    <div class="top-container cw-grid section-y-padding">
        <div class="cw-col-3 cw-col-xs-12">
            <img src="/images/hilja_logo.svg" height="94" width="250" alt="hilja logotyp"/>
            <p class="text-white mt-2">Logistik handlar inte bara om att flytta saker, det handlar om att få allt att fungera tillsammans</p>

        </div>
        <div class="cw-col-2 hide-mobile"></div>
        <div class="cw-col-2 cw-col-xs-12 link-container">
            <h4 class="text-full-white mb-2">Sidkarta</h4>
            <div class="d-flex flex-column gap-2">
                <a href="#intro">Intro</a>
                <a href="#om">Om oss</a>
                <a href="#process">Vår process</a>
                <a href="#erfarenhet">Vår erfarenhet</a>
                <a href="#kontakt">Kontakt</a>
            </div>
        </div>
        <div class="cw-col-2 cw-col-xs-12 link-container">
            <h4 class="text-full-white mb-2">Följ oss</h4>
            <div class="d-flex flex-column gap-2">
                <a href="https://www.linkedin.com/company/hilja-logistics/" target="_blank">LinkedIn</a>
                <a href="#kontakt">Facebook</a>
            </div>
        </div>
        <div class="cw-col-3 cw-col-xs-12 link-container">
            <h4 class="text-full-white mb-2">Kontakta oss</h4>
            <div class="d-flex flex-column gap-2">
                <p class="text-white">Planen 8, 518 90 Sandared</p>
                <a href="tel:+46705284448">+46 705 28 44 48</a>
                <a href="mailto:hilja@hiljalogistics.se">hilja@hiljalogistics.se</a>
            </div>
        </div>
    </div>
    <div class="bottom-container">
        <div></div>
        <div class="middle-container">
            <p class="text-full-white">&copy; Hilja Logistics 2025</p>
            <p class="text-full-white">Skapad av <a href="https://createweb.se" target="_blank">CreateWeb</a></p>
            <a href="/integritetspolicy">Integritetspolicy</a>
        </div>
        <div></div>
    </div>
</footer>

<style lang="scss">
    footer {
        .top-container {
            background-color: var(--color-bg-dark);
            padding-left: calc(50vw - var(--section-width) / 2);
            padding-right: calc(50vw - var(--section-width) / 2);
            padding-bottom: 5.625rem;

            img {
                width: 15.625rem;
                height: 5.875rem;
            }

            @media (max-width: 768px) {
                padding: 4rem 2rem;
                gap: 2rem;

                .link-container {
                    margin-bottom: 1rem;

                    &:last-of-type {
                        margin-bottom: 0;
                    }
                }

                img {
                    width: 14rem;
                }
            }

            @media (max-width: 1264px) {
                padding-left: 2rem;
                padding-right: 2rem;
            }
        }

        a {
            color: rgba(255,255,255, 0.50);
            width: fit-content;

            &:hover {
                color: white;
            }
        }

        .bottom-container {
            height: 3.2rem;
            background-color: var(--color-bg-dark-alt);
            display: grid;
            grid-template-columns: 1fr 75rem 1fr;

            @media (max-width: 768px) {
                grid-template-columns: 1fr;
                height: auto;
                padding: 2rem;
            }

            @media (max-width: 1264px) {
                padding-left: 2rem;
                padding-right: 2rem;
            }

            .middle-container {
                display: flex;
                align-items: center;
                justify-content: space-between;

                @media (max-width: 768px) {
                    flex-direction: column-reverse;
                    gap: 1rem;
                    align-items: flex-start;
                }
                
                * {
                    font-size: 0.875rem;
                    font-weight: 500;
                }
            }

            @media (max-width: 768px) {
                grid-template-columns: 1fr;
                height: auto;
            }
        }
    }
</style>