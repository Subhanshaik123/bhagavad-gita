<template>
    <footer class="site-footer">
        <!-- Decorative Background Elements -->
        <div class="footer-decoration footer-decoration-left"></div>
        <div class="footer-decoration footer-decoration-right"></div>

        <div class="footer-container">

            <!-- =====================================
                 MAIN FOOTER CONTENT
            ====================================== -->
            <div class="footer-main">

                <!-- Brand Section -->
                <div class="footer-brand-section">
                    <a href="/" class="footer-brand">

                        <!-- Replace this path with your actual logo -->
                        <img
    :src="'/images/logo-img.png'"
    alt="Bhagavad Gita Logo"
    class="footer-logo"
/>

                        <div class="brand-details">
                            <h2>BHAGAVAD GITA</h2>

                            <p>
                                Timeless Wisdom • A Better You
                            </p>
                        </div>
                    </a>

                    <div class="brand-ornament">
                        <span></span>
                        <i>◆</i>
                        <span></span>
                    </div>

                    <p class="brand-motto">
                        “Discern. Reflect. Live.”
                    </p>

                    <div class="brand-ornament bottom-ornament">
                        <span></span>
                        <i>◆</i>
                        <span></span>
                    </div>
                </div>


                <!-- Explore Links -->
                <div class="footer-column">
                    <h3>Explore</h3>

                    <nav class="footer-links">
                        <a href="/">Home</a>
                        <a href="#chapters">Chapters</a>
                        <a href="#slokas">Daily Sloka</a>
                        <a href="#wisdom">Wisdom for Life</a>
                        <a href="#resources">Resources</a>
                        <a href="#about">About</a>
                    </nav>
                </div>


                <!-- Support Links -->
                <div class="footer-column">
                    <h3>Support</h3>

                    <nav class="footer-links">
                        <a href="#faq">FAQ</a>
                        <a href="#contact">Contact</a>
                        <a href="#privacy">Privacy Policy</a>
                        <a href="#terms">Terms of Use</a>
                    </nav>
                </div>


                <!-- Stay Connected -->
                <div class="footer-column connected-column">
                    <h3>Stay Connected</h3>

                    <div class="social-links">

                        <a
                            href="#"
                            class="social-link"
                            aria-label="YouTube"
                        >
                            <span>▶</span>
                        </a>

                        <a
                            href="#"
                            class="social-link"
                            aria-label="Instagram"
                        >
                            <span>◎</span>
                        </a>

                        <a
                            href="#"
                            class="social-link"
                            aria-label="Facebook"
                        >
                            <span>f</span>
                        </a>

                        <a
                            href="#"
                            class="social-link"
                            aria-label="X"
                        >
                            <span>𝕏</span>
                        </a>

                        <a
                            href="#"
                            class="social-link"
                            aria-label="LinkedIn"
                        >
                            <span>in</span>
                        </a>

                    </div>

                    <div class="connected-ornament">
                        <span></span>
                        <i>◆</i>
                        <span></span>
                    </div>

                    <h4>Join our journey</h4>

                    <div class="small-gold-line"></div>

                    <p class="connected-text">
                        Get inspired with daily wisdom.
                    </p>
                </div>

            </div>


            <!-- =====================================
                 DECORATIVE DIVIDER
            ====================================== -->
            <div class="footer-divider">
                <span class="divider-line"></span>

                <span class="divider-ornament">
                    <i></i>
                    <b>✧</b>
                    <i></i>
                </span>

                <span class="divider-line"></span>
            </div>


            <!-- =====================================
                 BOTTOM FOOTER
            ====================================== -->
            <div class="footer-bottom">

                <p class="copyright">
                    © 2026 Bhagavad Gita. All rights reserved.
                </p>

                <div class="footer-message">
                    <span class="sanskrit-text">
                        सर्वे भवन्तु सुखिनः
                    </span>

                    <span class="message-divider">|</span>

                    <span class="english-message">
                        May all beings be happy.
                    </span>
                </div>

            </div>

        </div>
    </footer>
</template>


<style scoped>
/* =========================================
   FOOTER BASE
========================================= */

.site-footer {
    position: relative;
    width: 100%;
    overflow: hidden;

    color: #eee8d8;

    background:
        radial-gradient(
            ellipse at 50% 0%,
            rgba(17, 58, 67, 0.58) 0%,
            transparent 48%
        ),
        linear-gradient(
            135deg,
            #061a23 0%,
            #08232c 48%,
            #061821 100%
        );

    border-top: 1px solid rgba(218, 166, 70, 0.3);
}


/* =========================================
   DECORATIVE SIDE PATTERNS
========================================= */

.footer-decoration {
    position: absolute;
    top: 0;
    bottom: 0;

    width: 230px;
    opacity: 0.18;
    pointer-events: none;
}

.footer-decoration-left {
    left: -125px;

    background:
        repeating-radial-gradient(
            ellipse at center,
            transparent 0 18px,
            rgba(213, 160, 67, 0.8) 19px 20px,
            transparent 21px 37px
        );

    transform: rotate(25deg);
}

.footer-decoration-right {
    right: -125px;

    background:
        repeating-radial-gradient(
            ellipse at center,
            transparent 0 18px,
            rgba(213, 160, 67, 0.8) 19px 20px,
            transparent 21px 37px
        );

    transform: rotate(-25deg);
}


/* =========================================
   CONTAINER
========================================= */

.footer-container {
    position: relative;
    z-index: 2;

    width: min(1180px, 88%);
    margin: 0 auto;
}


/* =========================================
   MAIN FOOTER
========================================= */

.footer-main {
    display: grid;
    grid-template-columns:
        1.25fr
        0.85fr
        0.85fr
        1.15fr;

    gap: 55px;

    padding: 48px 0 42px;
}


/* =========================================
   BRAND SECTION
========================================= */

.footer-brand-section {
    display: flex;
    flex-direction: column;
    align-items: flex-start;
}

.footer-brand {
    display: flex;
    align-items: center;
    gap: 18px;

    color: inherit;
    text-decoration: none;
}

.footer-logo {
    width: 68px;
    height: 68px;

    object-fit: contain;
    object-position: center;

    filter:
        drop-shadow(0 0 8px rgba(225, 171, 70, 0.18));
}

.brand-details h2 {
    margin: 0;

    color: #f1e9d5;
    font-family: Georgia, 'Times New Roman', serif;
    font-size: 24px;
    font-weight: 600;
    letter-spacing: 1px;
    line-height: 1.1;
}

.brand-details p {
    margin: 8px 0 0;

    color: #b5b8ae;
    font-family: Georgia, 'Times New Roman', serif;
    font-size: 11px;
    letter-spacing: 0.2px;
}


/* =========================================
   BRAND ORNAMENT
========================================= */

.brand-ornament {
    width: 190px;
    margin: 27px 0 20px;

    display: flex;
    align-items: center;
    gap: 10px;
}

.brand-ornament span {
    height: 1px;
    flex: 1;
    background: #a9782f;
}

.brand-ornament i {
    color: #dba64b;
    font-size: 10px;
    font-style: normal;
}

.bottom-ornament {
    margin: 20px 0 0;
}

.brand-motto {
    margin: 0;

    color: #eee6d2;
    font-family: Georgia, 'Times New Roman', serif;
    font-size: 16px;
    font-style: italic;
    line-height: 1.5;
}


/* =========================================
   FOOTER COLUMNS
========================================= */

.footer-column {
    min-width: 0;
}

.footer-column h3 {
    margin: 3px 0 24px;

    color: #e2ad51;
    font-family: Georgia, 'Times New Roman', serif;
    font-size: 20px;
    font-weight: 600;
    line-height: 1;
}

.footer-links {
    display: flex;
    flex-direction: column;
    align-items: flex-start;
    gap: 17px;
}

.footer-links a {
    color: #d4d8d1;

    font-size: 13px;
    font-weight: 400;
    line-height: 1.2;
    text-decoration: none;

    transition:
        color 0.25s ease,
        transform 0.25s ease;
}

.footer-links a:hover {
    color: #e4b45b;
    transform: translateX(4px);
}


/* =========================================
   SOCIAL LINKS
========================================= */

.connected-column {
    padding-left: 5px;
}

.social-links {
    display: flex;
    align-items: center;
    gap: 12px;
}

.social-link {
    width: 38px;
    height: 38px;

    display: flex;
    align-items: center;
    justify-content: center;

    border: 1px solid #a8752e;
    border-radius: 50%;

    color: #e8dfc9;
    background: rgba(5, 27, 35, 0.35);

    font-size: 15px;
    font-weight: 600;
    text-decoration: none;

    transition:
        color 0.3s ease,
        background 0.3s ease,
        border-color 0.3s ease,
        transform 0.3s ease;
}

.social-link:first-child span {
    font-size: 11px;
}

.social-link:last-child span {
    font-size: 12px;
}

.social-link:hover {
    color: #17252a;
    background: #dca64b;
    border-color: #dca64b;
    transform: translateY(-4px);
}


/* =========================================
   CONNECTED ORNAMENT
========================================= */

.connected-ornament {
    width: 190px;
    margin: 28px 0 24px;

    display: flex;
    align-items: center;
    gap: 10px;
}

.connected-ornament span {
    flex: 1;
    height: 1px;
    background: #9c6d2b;
}

.connected-ornament i {
    color: #dca64b;
    font-size: 10px;
    font-style: normal;
}

.connected-column h4 {
    margin: 0;

    color: #f0e8d6;
    font-family: Georgia, 'Times New Roman', serif;
    font-size: 18px;
    font-style: italic;
    font-weight: 500;
}

.small-gold-line {
    width: 70px;
    height: 2px;
    margin-top: 17px;

    background: #dca64b;
}

.connected-text {
    margin: 16px 0 0;

    color: #aeb5af;
    font-size: 12px;
    line-height: 1.6;
}


/* =========================================
   MAIN DIVIDER
========================================= */

.footer-divider {
    display: flex;
    align-items: center;
    gap: 18px;
}

.divider-line {
    flex: 1;
    height: 1px;
    background: rgba(211, 162, 71, 0.65);
}

.divider-ornament {
    display: flex;
    align-items: center;
    gap: 8px;
}

.divider-ornament i {
    width: 6px;
    height: 6px;

    display: block;

    border: 1px solid #dba64b;
    transform: rotate(45deg);
}

.divider-ornament b {
    color: #dba64b;
    font-size: 28px;
    font-weight: 400;
    line-height: 1;
}


/* =========================================
   BOTTOM FOOTER
========================================= */

.footer-bottom {
    min-height: 76px;

    display: flex;
    align-items: center;
    justify-content: space-between;
    gap: 25px;
}

.copyright {
    margin: 0;

    color: #8fa19e;
    font-size: 11px;
    line-height: 1.5;
}

.footer-message {
    display: flex;
    align-items: center;
    gap: 12px;

    color: #c4c6bb;
    font-size: 13px;
    line-height: 1.5;
}

.sanskrit-text {
    color: #dca64b;
    font-family: Georgia, 'Times New Roman', serif;
    font-size: 17px;
}

.message-divider {
    color: #8d6b39;
    margin:20px;
}

.english-message {
    font-size: 20px;
    color: #c4c6bb;
}


/* =========================================
   TABLET
========================================= */

@media (max-width: 1050px) {
    .footer-main {
        grid-template-columns:
            1.2fr
            0.8fr
            0.8fr
            1fr;

        gap: 30px;
    }

    .brand-details h2 {
        font-size: 20px;
    }

    .footer-column h3 {
        font-size: 18px;
    }

    .footer-links a {
        font-size: 12px;
    }

    .social-links {
        gap: 8px;
    }

    .social-link {
        width: 34px;
        height: 34px;
    }
}


/* =========================================
   MOBILE
========================================= */

@media (max-width: 760px) {
    .footer-container {
        width: 88%;
    }

    .footer-main {
        grid-template-columns: 1fr 1fr;
        gap: 42px 28px;
        padding: 45px 0 38px;
    }

    .footer-brand-section {
        grid-column: 1 / -1;
        align-items: center;
        text-align: center;
    }

    .footer-brand {
        justify-content: center;
    }

    .brand-ornament {
        margin-left: auto;
        margin-right: auto;
    }

    .footer-column h3 {
        margin-bottom: 20px;
        font-size: 18px;
    }

    .footer-links {
        gap: 14px;
    }

    .footer-links a {
        font-size: 12px;
    }

    .connected-column {
        padding-left: 0;
    }

    .social-links {
        flex-wrap: wrap;
    }

    .connected-ornament {
        width: 100%;
        max-width: 190px;
    }

    .footer-bottom {
        min-height: auto;
        padding: 22px 0;

        flex-direction: column;
        justify-content: center;
        text-align: center;
        gap: 14px;
    }

    .footer-message {
        flex-wrap: wrap;
        justify-content: center;
        font-size: 11px;
    }

    .sanskrit-text {
        font-size: 15px;
    }
}


/* =========================================
   SMALL MOBILE
========================================= */

@media (max-width: 450px) {
    .footer-main {
        grid-template-columns: 1fr;
        gap: 35px;
    }

    .footer-column {
        text-align: center;
    }

    .footer-column h3 {
        text-align: center;
    }

    .footer-links {
        align-items: center;
    }

    .connected-column {
        display: flex;
        flex-direction: column;
        align-items: center;
    }

    .footer-brand {
        flex-direction: column;
        gap: 10px;
    }

    .brand-details h2 {
        font-size: 21px;
    }

    .brand-details p {
        font-size: 10px;
    }

    .brand-motto {
        font-size: 15px;
    }

    .footer-decoration {
        opacity: 0.1;
    }
}
</style>