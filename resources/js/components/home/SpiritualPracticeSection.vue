<template>
    <section class="spiritual-practice-section" id="practice">
        <div class="spiritual-practice-container">

            <!-- Header -->
            <div class="practice-header">
                <span class="practice-eyebrow">
                    Make Wisdom a Daily Habit
                </span>

                <h2>
                    Begin Your
                    <span>Spiritual Journey</span>
                </h2>

                <p>
                    Small daily practices can bring clarity, peace, and
                    meaningful transformation into your life.
                </p>
            </div>

            <!-- Practice Cards -->
            <div class="practice-grid">

                <!-- Daily Sloka -->
                <article class="practice-card practice-card-gold">
                    <div class="practice-card-icon">
                        ॐ
                    </div>

                    <div class="practice-card-number">
                        01
                    </div>

                    <div class="practice-card-content">
                        <span class="practice-card-label">
                            Daily Learning
                        </span>

                        <h3>
                            Daily Sloka
                        </h3>

                        <p>
                            Learn one powerful verse every day and discover
                            how its wisdom applies to your life.
                        </p>

                        <a href="#Chapters" class="practice-card-link">
                            Start Learning
                            <span>→</span>
                        </a>
                    </div>
                </article>

                <!-- Listen and Reflect -->
                <article class="practice-card practice-card-blue">
                    <div class="practice-card-icon">
                        ◉
                    </div>

                    <div class="practice-card-number">
                        02
                    </div>

                    <div class="practice-card-content">
                        <span class="practice-card-label">
                            Listen & Reflect
                        </span>

                        <h3>
                            Listen & Reflect
                        </h3>

                        <p>
                            Watch meaningful explanations and reflect on the
                            deeper message of every teaching.
                        </p>

                        <a href="https://www.youtube.com/watch?v=GmnIGdoxGBs" class="practice-card-link">
                            Explore Videos
                            <span>→</span>
                        </a>
                    </div>
                </article>

                <!-- Track Journey -->
                <article class="practice-card practice-card-green">
                    <div class="practice-card-icon">
                        ✦
                    </div>

                    <div class="practice-card-number">
                        03
                    </div>

                    <div class="practice-card-content">
                        <span class="practice-card-label">
                            Your Progress
                        </span>

                        <h3>
                            Track Your Journey
                        </h3>

                        <p>
                            Save meaningful slokas, revisit your favourites,
                            and continue your learning journey.
                        </p>

                        <a href="#slokas" class="practice-card-link">
                            View Saved Slokas
                            <span>→</span>
                        </a>
                    </div>
                </article>

            </div>

        </div>
    </section>
</template>

<style scoped>
/* =========================================
   SPIRITUAL PRACTICE SECTION
========================================= */

.spiritual-practice-section {
    position: relative;
    padding: 110px 0;
    background: #17243d;
    overflow: hidden;
}

.spiritual-practice-section::before {
    content: '';
    position: absolute;
    top: -180px;
    left: -180px;
    width: 470px;
    height: 470px;
    border: 1px solid rgba(214, 173, 91, 0.13);
    border-radius: 50%;
    box-shadow:
        0 0 0 35px rgba(214, 173, 91, 0.025),
        0 0 0 70px rgba(214, 173, 91, 0.025),
        0 0 0 105px rgba(214, 173, 91, 0.025);
    pointer-events: none;
}

.spiritual-practice-section::after {
    content: 'ॐ';
    position: absolute;
    right: 4%;
    bottom: -125px;
    color: rgba(214, 173, 91, 0.035);
    font-family: Georgia, serif;
    font-size: 19rem;
    pointer-events: none;
}

.spiritual-practice-container {
    position: relative;
    z-index: 1;
    width: min(1180px, calc(100% - 48px));
    margin: 0 auto;
}

/* =========================================
   HEADER
========================================= */

.practice-header {
    max-width: 650px;
    margin: 0 auto 55px;
    text-align: center;
}

.practice-eyebrow {
    display: block;
    margin-bottom: 14px;
    color: #d6ad5b;
    font-size: 0.72rem;
    font-weight: 800;
    letter-spacing: 0.22em;
    text-transform: uppercase;
}

.practice-header h2 {
    margin: 0;
    color: #fffaf0;
    font-family: 'Playfair Display', Georgia, serif;
    font-size: clamp(2.4rem, 4vw, 3.8rem);
    font-weight: 600;
    line-height: 1.15;
}

.practice-header h2 span {
    color: #d6ad5b;
}

.practice-header p {
    max-width: 560px;
    margin: 22px auto 0;
    color: rgba(255, 250, 240, 0.58);
    font-size: 0.95rem;
    line-height: 1.8;
}

/* =========================================
   PRACTICE GRID
========================================= */

.practice-grid {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: 22px;
}

/* =========================================
   PRACTICE CARD
========================================= */

.practice-card {
    position: relative;
    min-height: 350px;
    padding: 32px;
    border: 1px solid rgba(255, 255, 255, 0.1);
    border-radius: 20px;
    overflow: hidden;
    transition:
        transform 0.35s ease,
        border-color 0.35s ease,
        box-shadow 0.35s ease;
}

.practice-card:hover {
    transform: translateY(-8px);
    border-color: rgba(214, 173, 91, 0.5);
    box-shadow: 0 25px 50px rgba(0, 0, 0, 0.2);
}

.practice-card-gold {
    background:
        radial-gradient(
            circle at 100% 0%,
            rgba(214, 173, 91, 0.2),
            transparent 42%
        ),
        linear-gradient(
            145deg,
            rgba(196, 145, 45, 0.16),
            rgba(255, 255, 255, 0.035)
        );
}

.practice-card-blue {
    background:
        radial-gradient(
            circle at 100% 0%,
            rgba(75, 132, 181, 0.2),
            transparent 42%
        ),
        linear-gradient(
            145deg,
            rgba(58, 107, 153, 0.16),
            rgba(255, 255, 255, 0.035)
        );
}

.practice-card-green {
    background:
        radial-gradient(
            circle at 100% 0%,
            rgba(83, 157, 119, 0.2),
            transparent 42%
        ),
        linear-gradient(
            145deg,
            rgba(61, 130, 92, 0.16),
            rgba(255, 255, 255, 0.035)
        );
}

.practice-card::before {
    content: '';
    position: absolute;
    right: -75px;
    bottom: -85px;
    width: 230px;
    height: 230px;
    border: 1px solid rgba(255, 255, 255, 0.06);
    border-radius: 50%;
    box-shadow:
        0 0 0 25px rgba(255, 255, 255, 0.018),
        0 0 0 50px rgba(255, 255, 255, 0.018);
    pointer-events: none;
}

.practice-card-icon {
    display: flex;
    align-items: center;
    justify-content: center;
    width: 58px;
    height: 58px;
    margin-bottom: 32px;
    border: 1px solid rgba(214, 173, 91, 0.25);
    border-radius: 18px;
    background: rgba(255, 250, 240, 0.06);
    color: #e5bd69;
    font-family: Georgia, serif;
    font-size: 1.7rem;
}

.practice-card-blue .practice-card-icon {
    color: #8bb9dd;
}

.practice-card-green .practice-card-icon {
    color: #9bd0ad;
}

.practice-card-number {
    position: absolute;
    top: 27px;
    right: 30px;
    color: rgba(255, 250, 240, 0.12);
    font-family: 'Playfair Display', Georgia, serif;
    font-size: 3rem;
    font-weight: 600;
}

.practice-card-content {
    position: relative;
    z-index: 1;
}

.practice-card-label {
    display: block;
    margin-bottom: 12px;
    color: #d6ad5b;
    font-size: 0.68rem;
    font-weight: 800;
    letter-spacing: 0.16em;
    text-transform: uppercase;
}

.practice-card-blue .practice-card-label {
    color: #8bb9dd;
}

.practice-card-green .practice-card-label {
    color: #9bd0ad;
}

.practice-card-content h3 {
    margin: 0 0 17px;
    color: #fffaf0;
    font-family: 'Playfair Display', Georgia, serif;
    font-size: 1.65rem;
    font-weight: 600;
    line-height: 1.25;
}

.practice-card-content p {
    max-width: 290px;
    margin: 0;
    color: rgba(255, 250, 240, 0.58);
    font-size: 0.88rem;
    line-height: 1.8;
}

.practice-card-link {
    display: inline-flex;
    align-items: center;
    gap: 10px;
    margin-top: 30px;
    color: #e5bd69;
    font-size: 0.78rem;
    font-weight: 800;
    text-decoration: none;
    transition: gap 0.25s ease;
}

.practice-card-blue .practice-card-link {
    color: #8bb9dd;
}

.practice-card-green .practice-card-link {
    color: #9bd0ad;
}

.practice-card-link:hover {
    gap: 16px;
}

.practice-card-link span {
    font-size: 1rem;
}

/* =========================================
   RESPONSIVE DESIGN
========================================= */

@media (max-width: 900px) {
    .practice-grid {
        grid-template-columns: 1fr;
        max-width: 600px;
        margin: 0 auto;
    }

    .practice-card {
        min-height: 290px;
    }
}

@media (max-width: 640px) {
    .spiritual-practice-section {
        padding: 80px 0;
    }

    .spiritual-practice-container {
        width: calc(100% - 32px);
    }

    .practice-header {
        margin-bottom: 38px;
    }

    .practice-header h2 {
        font-size: 2.5rem;
    }

    .practice-card {
        min-height: 310px;
        padding: 26px;
    }
}
</style>