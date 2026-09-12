<template>
    <section class="featured-slokas-section" id="slokas">
        <div class="featured-slokas-container">

            <!-- Header -->
            <div class="featured-slokas-header">
                <div>
                    <span class="featured-eyebrow">
                        Wisdom for Everyday Life
                    </span>

                    <h2>
                        Featured
                        <span>Slokas</span>
                    </h2>
                </div>

                <p>
                    Timeless guidance for modern challenges
                </p>
            </div>

            <!-- Sloka Cards -->
            <div class="featured-slokas-grid">
                <article
                    v-for="sloka in slokas"
                    :key="sloka.id"
                    class="featured-sloka-card"
                >
                    <div class="sloka-card-top">
                        <div>
                            <span class="sloka-chapter">
                                Chapter {{ sloka.chapter }}
                            </span>

                            <span class="sloka-verse">
                                Verse {{ sloka.verse }}
                            </span>
                        </div>

                        <button
                            type="button"
                            class="bookmark-button"
                            :class="{ saved: savedSlokas.includes(sloka.id) }"
                            :aria-label="`Save ${sloka.title}`"
                            @click="toggleBookmark(sloka.id)"
                        >
                            {{ savedSlokas.includes(sloka.id) ? '♥' : '♡' }}
                        </button>
                    </div>

                    <div class="sloka-divider"></div>

                    <h3>{{ sloka.title }}</h3>

                    <p class="sloka-sanskrit">
                        {{ sloka.sanskrit }}
                    </p>

                    <p class="sloka-transliteration">
                        {{ sloka.transliteration }}
                    </p>

                    <div class="sloka-meaning">
                        <span>Simple Meaning</span>
                        <p>{{ sloka.meaning }}</p>
                    </div>

                    <div class="sloka-card-bottom">
                        <span class="sloka-lesson">
                            ✦ Life Lesson
                        </span>

                        <a href="#slokas" class="read-sloka-link">
                            Read Sloka
                            <span>→</span>
                        </a>
                    </div>
                </article>
            </div>

            <!-- Bottom Button -->
            <div class="featured-slokas-action">
                <a href="#slokas" class="browse-slokas-button">
                    Browse All Slokas
                    <span>↗</span>
                </a>
            </div>

        </div>
    </section>
</template>

<script setup>
import { ref } from 'vue';

const savedSlokas = ref([]);

const toggleBookmark = (slokaId) => {
    if (savedSlokas.value.includes(slokaId)) {
        savedSlokas.value = savedSlokas.value.filter(
            (id) => id !== slokaId
        );
    } else {
        savedSlokas.value.push(slokaId);
    }
};

const slokas = [
    {
        id: 1,
        chapter: 2,
        verse: 47,
        title: 'Focus on Your Actions',
        sanskrit:
            'कर्मण्येवाधिकारस्ते मा फलेषु कदाचन',
        transliteration:
            'Karmanye vadhikaraste ma phaleshu kadachana',
        meaning:
            'You have the right to perform your duties, but not to the fruits of your actions.',
    },
    {
        id: 2,
        chapter: 2,
        verse: 20,
        title: 'The Eternal Soul',
        sanskrit:
            'न जायते म्रियते वा कदाचिन्',
        transliteration:
            'Na jayate mriyate va kadachin',
        meaning:
            'The soul is never born and never dies. It is eternal and everlasting.',
    },
    {
        id: 3,
        chapter: 6,
        verse: 5,
        title: 'Elevate Yourself',
        sanskrit:
            'उद्धरेदात्मनात्मानं नात्मानमवसादयेत्',
        transliteration:
            'Uddhared atmanatmanam natmanam avasadayet',
        meaning:
            'One must elevate oneself through one’s own mind and never allow oneself to fall.',
    },
    {
        id: 4,
        chapter: 4,
        verse: 7,
        title: 'Whenever Dharma Declines',
        sanskrit:
            'यदा यदा हि धर्मस्य ग्लानिर्भवति भारत',
        transliteration:
            'Yada yada hi dharmasya glanir bhavati Bharata',
        meaning:
            'Whenever righteousness declines and unrighteousness rises, the Divine manifests.',
    },
    {
        id: 5,
        chapter: 12,
        verse: 13,
        title: 'The Qualities of a Devotee',
        sanskrit:
            'अद्वेष्टा सर्वभूतानां मैत्रः करुण एव च',
        transliteration:
            'Adveshta sarva-bhutanam maitrah karuna eva cha',
        meaning:
            'A true devotee is friendly, compassionate, and free from hatred toward all beings.',
    },
    {
        id: 6,
        chapter: 18,
        verse: 66,
        title: 'The Path of Surrender',
        sanskrit:
            'सर्वधर्मान्परित्यज्य मामेकं शरणं व्रज',
        transliteration:
            'Sarva-dharman parityajya mam ekam sharanam vraja',
        meaning:
            'Surrender to the Divine with complete faith and receive freedom from all fears.',
    },
];
</script>

<style scoped>
/* =========================================
   FEATURED SLOKAS SECTION
========================================= */

.featured-slokas-section {
    position: relative;
    padding: 110px 0;
    background: #17243d;
    overflow: hidden;
}

.featured-slokas-section::before {
    content: '';
    position: absolute;
    top: -180px;
    right: -160px;
    width: 500px;
    height: 500px;
    border: 1px solid rgba(213, 168, 77, 0.13);
    border-radius: 50%;
    box-shadow:
        0 0 0 35px rgba(213, 168, 77, 0.025),
        0 0 0 70px rgba(213, 168, 77, 0.025),
        0 0 0 105px rgba(213, 168, 77, 0.025);
    pointer-events: none;
}

.featured-slokas-section::after {
    content: 'ॐ';
    position: absolute;
    bottom: -100px;
    left: 5%;
    color: rgba(213, 168, 77, 0.04);
    font-family: Georgia, serif;
    font-size: 18rem;
    pointer-events: none;
}

.featured-slokas-container {
    position: relative;
    z-index: 1;
    width: min(1180px, calc(100% - 48px));
    margin: 0 auto;
}

/* =========================================
   HEADER
========================================= */

.featured-slokas-header {
    display: flex;
    align-items: flex-end;
    justify-content: space-between;
    gap: 30px;
    margin-bottom: 48px;
}

.featured-eyebrow {
    display: block;
    margin-bottom: 13px;
    color: #d6ad5b;
    font-size: 0.72rem;
    font-weight: 800;
    letter-spacing: 0.22em;
    text-transform: uppercase;
}

.featured-slokas-header h2 {
    margin: 0;
    color: #fffaf0;
    font-family: 'Playfair Display', Georgia, serif;
    font-size: clamp(2.4rem, 4vw, 3.8rem);
    font-weight: 600;
    line-height: 1.1;
}

.featured-slokas-header h2 span {
    color: #d6ad5b;
}

.featured-slokas-header > p {
    margin: 0 0 7px;
    color: rgba(255, 250, 240, 0.55);
    font-family: 'Playfair Display', Georgia, serif;
    font-size: 0.95rem;
}

/* =========================================
   GRID
========================================= */

.featured-slokas-grid {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: 22px;
}

/* =========================================
   SLOKA CARD
========================================= */

.featured-sloka-card {
    position: relative;
    display: flex;
    flex-direction: column;
    min-height: 430px;
    padding: 28px;
    border: 1px solid rgba(214, 173, 91, 0.2);
    border-radius: 18px;
    background: linear-gradient(
        145deg,
        rgba(255, 252, 244, 0.1),
        rgba(255, 252, 244, 0.035)
    );
    backdrop-filter: blur(8px);
    transition:
        transform 0.35s ease,
        border-color 0.35s ease,
        background 0.35s ease;
}

.featured-sloka-card:hover {
    transform: translateY(-7px);
    border-color: rgba(214, 173, 91, 0.55);
    background: linear-gradient(
        145deg,
        rgba(255, 252, 244, 0.15),
        rgba(255, 252, 244, 0.055)
    );
}

.sloka-card-top {
    display: flex;
    align-items: flex-start;
    justify-content: space-between;
    gap: 15px;
}

.sloka-chapter,
.sloka-verse {
    display: inline-block;
    color: #d6ad5b;
    font-size: 0.72rem;
    font-weight: 800;
    letter-spacing: 0.07em;
    text-transform: uppercase;
}

.sloka-verse {
    margin-left: 12px;
    color: rgba(255, 250, 240, 0.45);
    font-weight: 600;
}

.bookmark-button {
    display: flex;
    align-items: center;
    justify-content: center;
    width: 34px;
    height: 34px;
    border: 1px solid rgba(214, 173, 91, 0.25);
    border-radius: 50%;
    background: transparent;
    color: rgba(255, 250, 240, 0.65);
    font-size: 1.25rem;
    cursor: pointer;
    transition:
        background 0.25s ease,
        color 0.25s ease,
        border-color 0.25s ease;
}

.bookmark-button:hover,
.bookmark-button.saved {
    border-color: #d6ad5b;
    background: rgba(214, 173, 91, 0.12);
    color: #e5bd69;
}

.sloka-divider {
    width: 100%;
    height: 1px;
    margin: 23px 0 25px;
    background: linear-gradient(
        to right,
        rgba(214, 173, 91, 0.35),
        transparent
    );
}

.featured-sloka-card h3 {
    margin: 0 0 18px;
    color: #fffaf0;
    font-family: 'Playfair Display', Georgia, serif;
    font-size: 1.45rem;
    font-weight: 600;
    line-height: 1.3;
}

.sloka-sanskrit {
    margin: 0 0 13px;
    color: #e5bd69;
    font-family: 'Noto Serif Devanagari', Georgia, serif;
    font-size: 1.15rem;
    line-height: 1.8;
}

.sloka-transliteration {
    margin: 0 0 25px;
    color: rgba(255, 250, 240, 0.55);
    font-family: 'Playfair Display', Georgia, serif;
    font-size: 0.88rem;
    font-style: italic;
    line-height: 1.6;
}

.sloka-meaning {
    padding: 17px 18px;
    border-left: 2px solid #b7832d;
    background: rgba(255, 250, 240, 0.045);
}

.sloka-meaning span {
    display: block;
    margin-bottom: 8px;
    color: #d6ad5b;
    font-size: 0.68rem;
    font-weight: 800;
    letter-spacing: 0.13em;
    text-transform: uppercase;
}

.sloka-meaning p {
    margin: 0;
    color: rgba(255, 250, 240, 0.72);
    font-size: 0.84rem;
    line-height: 1.7;
}

.sloka-card-bottom {
    display: flex;
    align-items: center;
    justify-content: space-between;
    gap: 15px;
    margin-top: auto;
    padding-top: 28px;
}

.sloka-lesson {
    color: rgba(255, 250, 240, 0.45);
    font-size: 0.72rem;
    font-weight: 700;
}

.read-sloka-link {
    display: inline-flex;
    align-items: center;
    gap: 8px;
    color: #d6ad5b;
    font-size: 0.78rem;
    font-weight: 800;
    text-decoration: none;
    transition: gap 0.25s ease;
}

.read-sloka-link:hover {
    gap: 13px;
}

/* =========================================
   BOTTOM BUTTON
========================================= */

.featured-slokas-action {
    display: flex;
    justify-content: center;
    margin-top: 48px;
}

.browse-slokas-button {
    display: inline-flex;
    align-items: center;
    gap: 13px;
    padding: 14px 25px;
    border: 1px solid rgba(214, 173, 91, 0.5);
    border-radius: 100px;
    color: #e5bd69;
    font-size: 0.78rem;
    font-weight: 800;
    text-decoration: none;
    transition:
        background 0.25s ease,
        color 0.25s ease,
        gap 0.25s ease;
}

.browse-slokas-button:hover {
    gap: 18px;
    background: #d6ad5b;
    color: #17243d;
}

/* =========================================
   RESPONSIVE DESIGN
========================================= */

@media (max-width: 950px) {
    .featured-slokas-grid {
        grid-template-columns: repeat(2, 1fr);
    }
}

@media (max-width: 640px) {
    .featured-slokas-section {
        padding: 80px 0;
    }

    .featured-slokas-container {
        width: calc(100% - 32px);
    }

    .featured-slokas-header {
        align-items: flex-start;
        flex-direction: column;
        gap: 12px;
        margin-bottom: 35px;
    }

    .featured-slokas-header h2 {
        font-size: 2.5rem;
    }

    .featured-slokas-grid {
        grid-template-columns: 1fr;
        gap: 18px;
    }

    .featured-sloka-card {
        min-height: 400px;
        padding: 24px;
    }
}
</style>