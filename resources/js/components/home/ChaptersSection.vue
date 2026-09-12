<template>
    <section class="chapter-showcase" id="chapters">
        <div class="chapter-showcase-container">

            <!-- Section Header -->
            <div class="chapter-header">
                <div>
                    <span class="chapter-eyebrow">
                        Explore the 18 Chapters
                    </span>

                    <h2>
                        A Journey Through
                        <span>Timeless Wisdom</span>
                    </h2>
                </div>

                <p class="chapter-header-description">
                    A journey through 700 timeless slokas
                </p>
            </div>

            <!-- Chapter Carousel -->
            <div class="chapter-carousel-wrapper">

                <!-- Previous Button -->
                <button
                    class="carousel-arrow carousel-arrow-left"
                    type="button"
                    aria-label="Previous chapters"
                    @click="scrollChapters('left')"
                >
                    <span>‹</span>
                </button>

                <!-- Cards Container -->
                <div
                    ref="chapterScroller"
                    class="chapter-carousel"
                >
                    <article
                        v-for="chapter in chapters"
                        :key="chapter.number"
                        class="chapter-slide"
                    >
                        <div
                            class="chapter-image"
                            :style="{
                                backgroundImage: `url(${chapter.image})`
                            }"
                        >
                            <div class="chapter-image-overlay"></div>

                            <div class="chapter-card-content">

                                <div class="chapter-card-number">
                                    {{ String(chapter.number).padStart(2, '0') }}
                                </div>

                                <div class="chapter-card-details">
                                    <span class="chapter-card-sanskrit">
                                        {{ chapter.sanskrit }}
                                    </span>

                                    <h3>
                                        {{ chapter.name }}
                                    </h3>

                                    <p>
                                        {{ chapter.description }}
                                    </p>
                                </div>

                            </div>
                        </div>
                    </article>
                </div>

                <!-- Next Button -->
                <button
                    class="carousel-arrow carousel-arrow-right"
                    type="button"
                    aria-label="Next chapters"
                    @click="scrollChapters('right')"
                >
                    <span>›</span>
                </button>

            </div>

            <!-- Bottom Action -->
            <div class="chapter-bottom-action">
                <a href="#chapters" class="view-all-chapters">
                    View All Chapters
                    <span>→</span>
                </a>
            </div>

        </div>
    </section>
</template>

<script setup>
import { ref } from 'vue';

const chapterScroller = ref(null);

const scrollChapters = (direction) => {
    if (!chapterScroller.value) {
        return;
    }

    const scrollAmount = chapterScroller.value.clientWidth * 0.85;

    chapterScroller.value.scrollBy({
        left: direction === 'right'
            ? scrollAmount
            : -scrollAmount,
        behavior: 'smooth',
    });
};

const chapters = [
    {
        number: 1,
        sanskrit: 'अर्जुन विषाद योग',
        name: 'Arjuna Vishada Yoga',
        image: '/images/chapters/chapter-01.png',
        description: 'The Yoga of Arjuna’s Dejection',
    },
    {
        number: 2,
        sanskrit: 'सांख्य योग',
        name: 'Sankhya Yoga',
        image: '/images/chapters/chapter-02.png',
        description: 'The Yoga of Knowledge',
    },
    {
        number: 3,
        sanskrit: 'कर्म योग',
        name: 'Karma Yoga',
        image: '/images/chapters/chapter-03.png',
        description: 'The Yoga of Selfless Action',
    },
    {
        number: 4,
        sanskrit: 'ज्ञान कर्म संन्यास योग',
        name: 'Jnana Karma Sannyasa Yoga',
        image: '/images/chapters/chapter-04.png',
        description: 'The Yoga of Knowledge and Renunciation',
    },
    {
        number: 5,
        sanskrit: 'कर्म संन्यास योग',
        name: 'Karma Sannyasa Yoga',
        image: '/images/chapters/chapter-05.png',
        description: 'The Yoga of Renunciation',
    },
    {
        number: 6,
        sanskrit: 'ध्यान योग',
        name: 'Dhyana Yoga',
        image: '/images/chapters/chapter-06.png',
        description: 'The Yoga of Meditation',
    },
    {
        number: 7,
        sanskrit: 'ज्ञान विज्ञान योग',
        name: 'Jnana Vijnana Yoga',
        image: '/images/chapters/chapter-07.png',
        description: 'The Yoga of Knowledge and Realization',
    },
    {
        number: 8,
        sanskrit: 'अक्षर ब्रह्म योग',
        name: 'Akshara Brahma Yoga',
        image: '/images/chapters/chapter-08.png',
        description: 'The Yoga of the Imperishable Absolute',
    },
    {
        number: 9,
        sanskrit: 'राज विद्या राज गुह्य योग',
        name: 'Raja Vidya Raja Guhya Yoga',
        image: '/images/chapters/chapter-09.png',
        description: 'The Yoga of Royal Knowledge',
    },
    {
        number: 10,
        sanskrit: 'विभूति योग',
        name: 'Vibhuti Yoga',
        image: '/images/chapters/chapter-10.png',
        description: 'The Yoga of Divine Manifestations',
    },
    {
        number: 11,
        sanskrit: 'विश्वरूप दर्शन योग',
        name: 'Vishvarupa Darshana Yoga',
        image: '/images/chapters/chapter-11.png',
        description: 'The Yoga of the Universal Form',
    },
    {
        number: 12,
        sanskrit: 'भक्ति योग',
        name: 'Bhakti Yoga',
        image: '/images/chapters/chapter-12.png',
        description: 'The Yoga of Devotion',
    },
    {
        number: 13,
        sanskrit: 'क्षेत्र क्षेत्रज्ञ विभाग योग',
        name: 'Kshetra Kshetrajna Vibhaga Yoga',
        image: '/images/chapters/chapter-13.png',
        description: 'The Yoga of Distinguishing Matter and Spirit',
    },
    {
        number: 14,
        sanskrit: 'गुणत्रय विभाग योग',
        name: 'Guna Traya Vibhaga Yoga',
        image: '/images/chapters/chapter-14.png',
        description: 'The Yoga of the Three Qualities',
    },
    {
        number: 15,
        sanskrit: 'पुरुषोत्तम योग',
        name: 'Purushottama Yoga',
        image: '/images/chapters/chapter-15.png',
        description: 'The Yoga of the Supreme Person',
    },
    {
        number: 16,
        sanskrit: 'दैवासुर सम्पद विभाग योग',
        name: 'Daivasura Sampad Vibhaga Yoga',
        image: '/images/chapters/chapter-16.png',
        description: 'The Yoga of Divine and Demonic Qualities',
    },
    {
        number: 17,
        sanskrit: 'श्रद्धात्रय विभाग योग',
        name: 'Shraddha Traya Vibhaga Yoga',
        image: '/images/chapters/chapter-17.png',
        description: 'The Yoga of the Three Divisions of Faith',
    },
    {
        number: 18,
        sanskrit: 'मोक्ष संन्यास योग',
        name: 'Moksha Sannyasa Yoga',
        image: '/images/chapters/chapter-18.png',
        description: 'The Yoga of Liberation and Renunciation',
    },
];
</script>

<style scoped>
/* =========================================
   CHAPTER SHOWCASE
========================================= */

.chapter-showcase {
    position: relative;
    padding: 72px 0 35px;
    background: #f7f2e8;
    overflow: hidden;
}

.chapter-showcase-container {
    width: min(100% - 48px, 1320px);
    margin: 0 auto;
}

/* =========================================
   HEADER
========================================= */

.chapter-header {
    display: flex;
    align-items: flex-end;
    justify-content: space-between;
    gap: 30px;
    margin-bottom: 28px;
}

.chapter-eyebrow {
    display: block;
    margin-bottom: 8px;
    color: #a87927;
    font-family: 'DM Sans', sans-serif;
    font-size: 0.75rem;
    font-weight: 800;
    letter-spacing: 0.18em;
    text-transform: uppercase;
}

.chapter-header h2 {
    margin: 0;
    color: #1a263c;
    font-family: 'Playfair Display', Georgia, serif;
    font-size: clamp(1.8rem, 3vw, 2.7rem);
    font-weight: 600;
    line-height: 1.2;
}

.chapter-header h2 span {
    color: #a87927;
}

.chapter-header-description {
    margin: 0 0 8px;
    color: #716e67;
    font-family: 'Playfair Display', Georgia, serif;
    font-size: 0.95rem;
    white-space: nowrap;
}

/* =========================================
   CAROUSEL
========================================= */

.chapter-carousel-wrapper {
    position: relative;
}

.chapter-carousel {
    display: flex;
    gap: 8px;
    padding: 0 2px 15px;
    overflow-x: auto;
    scroll-behavior: smooth;
    scroll-snap-type: x mandatory;
    scrollbar-width: none;
}

.chapter-carousel::-webkit-scrollbar {
    display: none;
}

.chapter-slide {
    flex: 0 0 calc((100% - 40px) / 6);
    min-width: 0;
    scroll-snap-align: start;
}

/* =========================================
   CHAPTER CARD
========================================= */

.chapter-image {
    position: relative;
    height: 265px;
    border: 1px solid rgba(183, 131, 45, 0.22);
    border-radius: 9px;
    background-position: center;
    background-size: cover;
    overflow: hidden;
    box-shadow: 0 8px 20px rgba(34, 38, 43, 0.08);
    transition:
        transform 0.35s ease,
        box-shadow 0.35s ease;
}

.chapter-image:hover {
    transform: translateY(-5px);
    box-shadow: 0 16px 30px rgba(34, 38, 43, 0.18);
}

.chapter-image-overlay {
    position: absolute;
    inset: 0;
    background:
        linear-gradient(
            to bottom,
            rgba(4, 15, 25, 0.03) 15%,
            rgba(4, 15, 25, 0.08) 35%,
            rgba(3, 13, 23, 0.92) 100%
        );
}

.chapter-card-content {
    position: relative;
    z-index: 1;
    display: flex;
    flex-direction: column;
    justify-content: flex-end;
    height: 100%;
    padding: 18px 13px 17px;
}

.chapter-card-number {
    position: absolute;
    top: 50px;
    left: 13px;
    color: #fff4d4;
    font-family: 'Playfair Display', Georgia, serif;
    font-size: 1.8rem;
    font-weight: 600;
    line-height: 1;
    text-shadow: 0 2px 8px rgba(0, 0, 0, 0.4);
}

.chapter-card-details {
    min-width: 0;
}

.chapter-card-sanskrit {
    display: block;
    margin-bottom: 7px;
    color: #f3c96a;
    font-size: 0.7rem;
    font-weight: 700;
    line-height: 1.3;
}

.chapter-card-details h3 {
    display: -webkit-box;
    margin: 0 0 9px;
    overflow: hidden;
    color: #fffaf0;
    font-family: 'Playfair Display', Georgia, serif;
    font-size: 0.95rem;
    font-weight: 600;
    line-height: 1.25;
    -webkit-box-orient: vertical;
    -webkit-line-clamp: 2;
}

.chapter-card-details p {
    display: -webkit-box;
    margin: 0;
    overflow: hidden;
    color: rgba(255, 250, 240, 0.82);
    font-size: 0.68rem;
    line-height: 1.4;
    -webkit-box-orient: vertical;
    -webkit-line-clamp: 2;
}

/* =========================================
   ARROW BUTTONS
========================================= */

.carousel-arrow {
    position: absolute;
    top: 50%;
    z-index: 5;
    display: flex;
    align-items: center;
    justify-content: center;
    width: 34px;
    height: 34px;
    border: 1px solid rgba(159, 117, 48, 0.25);
    border-radius: 50%;
    background: rgba(255, 252, 245, 0.95);
    color: #765722;
    font-size: 1.8rem;
    line-height: 1;
    cursor: pointer;
    transform: translateY(-50%);
    box-shadow: 0 5px 16px rgba(50, 40, 20, 0.1);
    transition:
        background 0.25s ease,
        color 0.25s ease,
        transform 0.25s ease;
}

.carousel-arrow:hover {
    background: #b7832d;
    color: #fffaf0;
    transform: translateY(-50%) scale(1.08);
}

.carousel-arrow-left {
    left: -17px;
}

.carousel-arrow-right {
    right: -17px;
}

.carousel-arrow span {
    position: relative;
    top: -2px;
}

/* =========================================
   BOTTOM ACTION
========================================= */

.chapter-bottom-action {
    display: flex;
    justify-content: flex-end;
    margin-top: 2px;
}

.view-all-chapters {
    display: inline-flex;
    align-items: center;
    gap: 9px;
    color: #263248;
    font-size: 0.78rem;
    font-weight: 800;
    text-decoration: none;
    transition:
        color 0.25s ease,
        gap 0.25s ease;
}

.view-all-chapters span {
    color: #263248;
    font-size: 1.1rem;
}

.view-all-chapters:hover {
    gap: 14px;
    color: #a87927;
}

/* =========================================
   RESPONSIVE DESIGN
========================================= */

@media (max-width: 1150px) {
    .chapter-slide {
        flex: 0 0 calc((100% - 24px) / 4);
    }
}

@media (max-width: 850px) {
    .chapter-showcase {
        padding: 60px 0 30px;
    }

    .chapter-header {
        align-items: flex-start;
        flex-direction: column;
        gap: 12px;
    }

    .chapter-header-description {
        margin: 0;
    }

    .chapter-slide {
        flex: 0 0 calc((100% - 16px) / 3);
    }
}

@media (max-width: 600px) {
    .chapter-showcase-container {
        width: calc(100% - 32px);
    }

    .chapter-header h2 {
        font-size: 2rem;
    }

    .chapter-header-description {
        font-size: 0.85rem;
    }

    .chapter-slide {
        flex: 0 0 calc((100% - 8px) / 2);
    }

    .chapter-image {
        height: 245px;
    }

    .chapter-card-content {
        padding: 15px 11px;
    }

    .chapter-card-number {
        top: 42px;
        left: 11px;
        font-size: 1.6rem;
    }

    .chapter-card-sanskrit {
        font-size: 0.65rem;
    }

    .chapter-card-details h3 {
        font-size: 0.85rem;
    }

    .chapter-card-details p {
        font-size: 0.65rem;
    }

    .carousel-arrow {
        width: 30px;
        height: 30px;
        font-size: 1.5rem;
    }

    .carousel-arrow-left {
        left: -12px;
    }

    .carousel-arrow-right {
        right: -12px;
    }
}

@media (max-width: 400px) {
    .chapter-slide {
        flex: 0 0 75%;
    }
}
</style>