<template>
    <section class="journey-section">

        <!-- =========================================
     TOP QUOTE BANNER
========================================== -->
<div class="quote-banner">
    <div class="quote-overlay"></div>

    <div class="quote-container">

        <!-- Guruji Image -->
        <div class="guruji-image-wrapper">
            <img
                :src="'/images/guruji.png'"
                alt="Guruji"
                class="guruji-image"
            />
        </div>


        <!-- Center Quote -->
        <div class="quote-content">
            <div class="quote-symbol"></div>

            <p class="quote-text">
                The Bhagavad Gita is not just a scripture to be read,
                <br />
                but a guide to be lived.
            </p>

            <p class="quote-author">
                — SRI SWAMI MUKUNDANANDA JI
            </p>
        </div>


        <!-- Watch Video Button -->
        <button
    type="button"
    class="watch-video-button"
    @click="openFeaturedVideo"
>
    <span>Watch Featured Videos</span>
    <span class="button-arrow">→</span>
</button>

    </div>
</div>


        <!-- =========================================
             TRUST STATISTICS SECTION
        ========================================== -->
        <div class="trust-section">
            <h3 class="trust-heading">
                Trusted by Seekers Worldwide
            </h3>

            <div class="trust-items">

                <!-- Item 1 -->
                <div class="trust-item">
                    <div class="trust-icon">◎</div>

                    <div class="trust-info">
                        <strong>1M+</strong>
                        <span>Readers Inspired</span>
                    </div>
                </div>

                <div class="trust-divider"></div>

                <!-- Item 2 -->
                <div class="trust-item">
                    <div class="trust-icon">♟</div>

                    <div class="trust-info">
                        <strong>700</strong>
                        <span>Timeless Slokas</span>
                    </div>
                </div>

                <div class="trust-divider"></div>

                <!-- Item 3 -->
                <div class="trust-item">
                    <div class="trust-icon">♥</div>

                    <div class="trust-info">
                        <strong>18</strong>
                        <span>Life-Changing Chapters</span>
                    </div>
                </div>

                <div class="trust-divider"></div>

                <!-- Item 4 -->
                <div class="trust-item">
                    <div class="trust-icon">♛</div>

                    <div class="trust-info">
                        <strong class="peaceful-title">
                            A More Peaceful
                            <br />
                            You
                        </strong>
                    </div>
                </div>

            </div>
        </div>


        <!-- =========================================
             BOTTOM JOURNEY CTA
        ========================================== -->
        <div class="journey-cta">
            <div class="journey-cta-overlay"></div>

            <div class="journey-cta-content">
                <h2>Begin Your Journey Today</h2>

                <p>
                    Timeless wisdom. A brighter tomorrow.
                </p>

                <a href="#chapters" class="explore-button">
                    <span>Explore the Bhagavad Gita</span>
                    <span class="button-arrow">→</span>
                </a>
            </div>
        </div>

    </section>
</template>

<script setup>
const openFeaturedVideo = () => {
    window.open(
        'https://www.youtube.com/watch?v=ukw0DMLwR4Y',
        '_blank',
        'noopener,noreferrer'
    );
};
</script>


<style scoped>
/* =========================================
   MAIN SECTION
========================================= */

.journey-section {
    width: 100%;
    overflow: hidden;
    background: #fff8e9;
}


/* =========================================
   TOP QUOTE BANNER
========================================= */

.quote-banner {
    position: relative;
    width: 100%;
    height: 270px;

    display: flex;
    align-items: center;

    background-image: url('/images/background-img.png');
    background-size: cover;
    background-position: center;
    background-repeat: no-repeat;
}

.quote-overlay {
    position: absolute;
    inset: 0;
    z-index: 1;

    background:
        linear-gradient(
            90deg,
            rgba(255, 248, 229, 0.9) 0%,
            rgba(255, 248, 229, 0.72) 25%,
            rgba(255, 248, 229, 0.52) 55%,
            rgba(255, 248, 229, 0.12) 100%
        );
}

.quote-container {
    position: relative;
    z-index: 2;

    width: min(1250px, 94%);
    height: 100%;
    margin: 0 auto;

    display: grid;
    grid-template-columns: 250px 1fr 250px;
    align-items: center;
    gap: 25px;
}


/* =========================================
   GURUJI IMAGE - LEFT SIDE
========================================= */

.guruji-image-wrapper {
    align-self: end;

    height: 100%;
    display: flex;
    align-items: flex-end;
    justify-content: center;
}

.guruji-image {
    display: block;

    width: 245px;
    height: 255px;

    object-fit: contain;
    object-position: bottom center;

    filter:
        drop-shadow(0 8px 14px rgba(56, 38, 20, 0.14));

    transition:
        transform 0.4s ease,
        filter 0.4s ease;
}

.guruji-image:hover {
    transform: translateY(-5px) scale(1.02);

    filter:
        drop-shadow(0 12px 20px rgba(56, 38, 20, 0.2));
}


/* =========================================
   CENTER QUOTE CONTENT
========================================= */

.quote-content {
    position: relative;

    width: 100%;
    max-width: 610px;
    margin: 0 auto;

    padding: 0 15px;

    text-align: center;
}

.quote-symbol {
    position: absolute;
    top: -38px;
    left: 50%;

    color: #70491f;
    font-family: Georgia, 'Times New Roman', serif;
    font-size: 48px;
    font-weight: 700;
    line-height: 1;

    transform: translateX(-50%);
}

.quote-text {
    margin: 0 0 15px;

    color: #563719;
    font-family: Georgia, 'Times New Roman', serif;
    font-size: 20px;
    font-style: italic;
    font-weight: 600;
    line-height: 1.55;
}

.quote-author {
    margin: 0;

    color: #80613c;
    font-family: Georgia, 'Times New Roman', serif;
    font-size: 10px;
    font-weight: 700;
    letter-spacing: 2px;
}


/* =========================================
   WATCH VIDEO BUTTON - RIGHT SIDE
========================================= */

.watch-video-button {
    justify-self: end;

    display: inline-flex;
    align-items: center;
    justify-content: center;
    gap: 15px;

    min-width: 190px;
    padding: 15px 18px;

    border: 1px solid rgba(130, 86, 32, 0.35);
    border-radius: 9px;

    color: #5b3b1b;
    background: rgba(248, 207, 126, 0.92);

    box-shadow:
        0 5px 12px rgba(77, 45, 13, 0.12),
        inset 0 1px 0 rgba(255, 255, 255, 0.45);

    font-size: 10px;
    font-weight: 700;
    text-decoration: none;
    white-space: nowrap;

    transition:
        color 0.3s ease,
        background 0.3s ease,
        transform 0.3s ease,
        box-shadow 0.3s ease;
}

.button-arrow {
    font-size: 16px;

    transition: transform 0.3s ease;
}

.watch-video-button:hover {
    color: #fff8e9;
    background: #9a682f;

    transform: translateY(-3px);

    box-shadow:
        0 10px 20px rgba(77, 45, 13, 0.18);
}

.watch-video-button:hover .button-arrow {
    transform: translateX(4px);
}

/* =========================================
   TRUST SECTION
========================================= */

.trust-section {
    position: relative;

    min-height: 165px;
    padding: 28px 6% 32px;

    background:
        linear-gradient(
            90deg,
            rgba(255, 249, 233, 0.98),
            rgba(255, 246, 221, 0.96),
            rgba(255, 249, 233, 0.98)
        );

    border-top: 1px solid rgba(143, 101, 46, 0.12);
    border-bottom: 1px solid rgba(143, 101, 46, 0.12);
}

.trust-heading {
    margin: 0 0 28px;

    color: #33291d;
    font-family: Georgia, 'Times New Roman', serif;
    font-size: 14px;
    font-weight: 600;
    text-align: center;
}

.trust-items {
    width: min(1050px, 100%);
    margin: 0 auto;

    display: flex;
    align-items: center;
    justify-content: space-between;
    gap: 25px;
}

.trust-item {
    position: relative;
    flex: 1;

    display: flex;
    align-items: center;
    justify-content: center;
    gap: 10px;

    padding: 18px 22px;
    border-radius: 12px;

    cursor: pointer;

    transition:
        transform 0.35s ease,
        background 0.35s ease,
        box-shadow 0.35s ease;
}

/* Soft gold glow under each item */
.trust-item::before {
    content: '';
    position: absolute;
    inset: 8px;

    border-radius: 12px;

    background: radial-gradient(
        circle at center,
        rgba(202, 146, 53, 0.18),
        transparent 72%
    );

    opacity: 0;
    transform: scale(0.75);

    transition:
        opacity 0.35s ease,
        transform 0.35s ease;

    pointer-events: none;
}

/* Small gold line at the bottom */
.trust-item::after {
    content: '';
    position: absolute;
    left: 50%;
    bottom: 5px;

    width: 0;
    height: 2px;

    border-radius: 10px;
    background: #b47a28;

    transform: translateX(-50%);

    transition: width 0.35s ease;
}

.trust-item:hover {
    transform: translateY(-7px);

    background: rgba(255, 255, 255, 0.38);

    box-shadow:
        0 10px 24px rgba(116, 77, 25, 0.08),
        inset 0 0 0 1px rgba(184, 130, 48, 0.12);
}

.trust-item:hover::before {
    opacity: 1;
    transform: scale(1);
}

.trust-item:hover::after {
    width: 45px;
}

.trust-icon {
    position: relative;
    z-index: 1;

    width: 38px;
    height: 38px;

    display: flex;
    align-items: center;
    justify-content: center;

    color: #996625;
    font-size: 28px;
    font-weight: 700;
    line-height: 1;

    transition:
        color 0.35s ease,
        transform 0.35s ease,
        text-shadow 0.35s ease;
}

.trust-item:hover .trust-icon {
    color: #b8791f;

    transform:
        translateY(-3px)
        scale(1.18);

    text-shadow:
        0 0 12px rgba(191, 132, 42, 0.4);
}

.trust-info {
    position: relative;
    z-index: 1;

    display: flex;
    flex-direction: column;
    align-items: flex-start;

    transition: transform 0.35s ease;
}

.trust-item:hover .trust-info {
    transform: translateX(3px);
}

.trust-info strong {
    color: #33291d;
    font-family: Georgia, 'Times New Roman', serif;
    font-size: 17px;
    font-weight: 500;
    line-height: 1.1;

    transition:
        color 0.35s ease,
        letter-spacing 0.35s ease;
}

.trust-item:hover .trust-info strong {
    color: #9a641e;
    letter-spacing: 0.4px;
}

.trust-info span {
    margin-top: 4px;

    color: #816c50;
    font-family: Georgia, 'Times New Roman', serif;
    font-size: 8px;
    line-height: 1.3;

    transition: color 0.35s ease;
}

.trust-item:hover .trust-info span {
    color: #9a794b;
}

.trust-info strong {
    color: #33291d;
    font-family: Georgia, 'Times New Roman', serif;
    font-size: 17px;
    font-weight: 500;
    line-height: 1.1;
}

.trust-info span {
    margin-top: 4px;

    color: #816c50;
    font-family: Georgia, 'Times New Roman', serif;
    font-size: 8px;
    line-height: 1.3;
}
.trust-item:hover .peaceful-title {
    color: #9a641e !important;
}
.peaceful-title {
    color: #33291d !important;
    font-family: Georgia, 'Times New Roman', serif;
    font-size: 9px !important;
    font-weight: 700 !important;
    line-height: 1.3 !important;
}

.trust-divider {
    width: 1px;
    height: 55px;
    background: rgba(137, 98, 49, 0.18);
}

/* =========================================
   TABLET RESPONSIVE
========================================= */

@media (max-width: 1000px) {
    .quote-container {
        grid-template-columns: 190px 1fr 205px;
        gap: 15px;
    }

    .guruji-image {
        width: 190px;
        height: 235px;
    }

    .quote-text {
        font-size: 17px;
    }

    .watch-video-button {
        min-width: 170px;
        padding: 13px 12px;
        font-size: 9px;
    }
}


/* =========================================
   MOBILE RESPONSIVE
========================================= */

@media (max-width: 700px) {
    .quote-banner {
        height: 470px;
    }

    .quote-overlay {
        background:
            linear-gradient(
                180deg,
                rgba(255, 248, 229, 0.9) 0%,
                rgba(255, 248, 229, 0.7) 55%,
                rgba(255, 248, 229, 0.35) 100%
            );
    }

    .quote-container {
        width: 90%;
        height: 100%;

        display: flex;
        flex-direction: column;
        justify-content: center;
        align-items: center;

        gap: 18px;
    }

    .guruji-image-wrapper {
        height: 190px;
        align-self: center;
    }

    .guruji-image {
        width: 190px;
        height: 200px;
    }

    .quote-content {
        max-width: 100%;
        padding: 0;
    }

    .quote-symbol {
        top: -32px;
        font-size: 38px;
    }

    .quote-text {
        font-size: 17px;
        line-height: 1.45;
    }

    .quote-text br {
        display: none;
    }

    .quote-author {
        font-size: 8px;
        letter-spacing: 1.3px;
    }

    .watch-video-button {
        justify-self: center;
        min-width: auto;
        padding: 13px 18px;
    }
}
/* =========================================
   BOTTOM JOURNEY CTA
========================================= */

.journey-cta {
    position: relative;
    width: 100%;
    min-height: 370px;

    display: flex;
    align-items: center;
    justify-content: center;

    /*
     * Replace this with your BOTTOM background image.
     * Example:
     * background-image: url('/images/journey-background.jpg');
     */
    background-image: url('/images/background.png');

    background-size: cover;
    background-position: center;
    background-repeat: no-repeat;
}

.journey-cta-overlay {
    position: absolute;
    inset: 0;

    background:
        linear-gradient(
            180deg,
            rgba(255, 235, 186, 0.15) 0%,
            rgba(52, 47, 35, 0.32) 55%,
            rgba(25, 38, 35, 0.56) 100%
        );
}

.journey-cta-content {
    position: relative;
    z-index: 2;

    padding: 35px 20px;
    text-align: center;
}

.journey-cta-content h2 {
    margin: 0;

    color: #261d14;
    font-family: Georgia, 'Times New Roman', serif;
    font-size: clamp(25px, 3vw, 34px);
    font-weight: 500;
    line-height: 1.2;
}

.journey-cta-content p {
    margin: 8px 0 17px;

    color: #59442a;
    font-family: Georgia, 'Times New Roman', serif;
    font-size: 11px;
    line-height: 1.5;
}

.explore-button {
    display: inline-flex;
    align-items: center;
    justify-content: center;
    gap: 13px;

    padding: 12px 20px;

    border: 1px solid rgba(0, 8, 19, 0.4);
    border-radius: 8px;

    color: #5b3b1b;
    background: #f2c978;

    box-shadow:
        0 6px 15px rgba(65, 43, 17, 0.16),
        inset 0 1px 0 rgba(255, 255, 255, 0.45);

    font-size: 10px;
    font-weight: 700;
    text-decoration: none;

    transition: all 0.3s ease;
}

.explore-button .button-arrow {
    font-size: 16px;
}

.explore-button:hover {
    color: #fff8e9;
    background: #f2c978;
    transform: translateY(-2px);
}

.explore-button:hover .button-arrow {
    transform: translateX(4px);
}


/* =========================================
   TABLET RESPONSIVE
========================================= */

@media (max-width: 900px) {
    .quote-container {
        width: 90%;
    }

    .quote-text {
        font-size: 16px;
    }

    .watch-video-button {
        min-width: 175px;
        padding: 12px 14px;
    }

    .trust-items {
        gap: 15px;
    }
}


/* =========================================
   MOBILE RESPONSIVE
========================================= */

@media (max-width: 650px) {
    .quote-banner {
        height: 300px;
    }

    .quote-overlay {
        background:
            linear-gradient(
                180deg,
                rgba(255, 248, 229, 0.95) 0%,
                rgba(255, 248, 229, 0.78) 60%,
                rgba(255, 248, 229, 0.35) 100%
            );
    }

    .quote-container {
        width: 88%;
        height: 100%;

        flex-direction: column;
        align-items: flex-start;
        justify-content: center;
        gap: 25px;
    }

    .quote-text {
        font-size: 18px;
    }

    .quote-text br {
        display: none;
    }

    .quote-author {
        font-size: 8px;
        letter-spacing: 1.3px;
    }

    .watch-video-button {
        min-width: auto;
        font-size: 10px;
    }

    .trust-section {
        padding: 20px 12px;
    }

    .trust-items {
        display: grid;
        grid-template-columns: repeat(2, 1fr);
        gap: 22px 10px;
    }

    .trust-divider {
        display: none;
    }

    .trust-item {
        justify-content: flex-start;
    }

    .trust-heading {
        font-size: 15px;
        margin-bottom: 20px;
    }

    .journey-cta {
        min-height: 260px;
    }

    .journey-cta-content h2 {
        font-size: 28px;
    }
}


/* =========================================
   SMALL MOBILE
========================================= */

@media (max-width: 400px) {
    .quote-text {
        font-size: 16px;
    }

    .trust-icon {
        font-size: 24px;
    }

    .trust-info strong {
        font-size: 15px;
    }

    .trust-info span {
        font-size: 7px;
    }

    .journey-cta-content h2 {
        font-size: 25px;
    }
}
@media (max-width: 650px) {
    .trust-item {
        padding: 16px 12px;
    }

    .trust-item:hover {
        transform: translateY(-4px);
    }

    .trust-item::after {
        bottom: 2px;
    }
}
</style>