<script setup>
import { ref, onMounted, onBeforeUnmount } from 'vue';

const backgroundImages = [
    '/images/hero-krishna-arjuna.jpg',
    '/images/hero-2.jpg',
    '/images/hero-3.jpg',
];

const currentImageIndex = ref(0);

let imageInterval;

onMounted(() => {
    imageInterval = setInterval(() => {
        currentImageIndex.value =
            (currentImageIndex.value + 1) % backgroundImages.length;
    }, 4000);
});

onBeforeUnmount(() => {
    clearInterval(imageInterval);
});

</script>

<template>
    <section class="cinematic-hero">
        <div
            v-for="(image, index) in backgroundImages"
            :key="image"
            class="hero-background"
            :class="{ active: currentImageIndex === index }"
            :style="{ backgroundImage: `url('${image}')` }"
        ></div>

        <div class="hero-dark-overlay"></div>
        <div class="hero-gold-glow"></div>

        <div class="hero-container">
            <div class="hero-main-content">
                <p class="hero-overline">
                    MORE THAN A SCRIPTURE
                </p>

                <h1>
                    Ancient Wisdom
                    <span>For A Brighter You.</span>
                </h1>

                <p class="hero-description">
                    Explore the Bhagavad Gita — one sloka at a time.
                    <br />
                    Find clarity, peace, and purpose for your everyday life.
                </p>

                <div class="hero-button-group">
                    <router-link to="/chapters" class="gold-hero-button">
                        Begin Your Journey
                        <span>→</span>
                    </router-link>

                    <button class="watch-hero-button">
                        <span class="watch-circle">▶</span>
                        Watch Introduction
                    </button>
                </div>

                <div class="hero-statistics">
                    <div class="hero-stat">
                        <div class="stat-icon">◉</div>

                        <div>
                            <strong>18</strong>
                            <small>Chapters</small>
                        </div>
                    </div>

                    <div class="hero-stat">
                        <div class="stat-icon">✥</div>

                        <div>
                            <strong>700</strong>
                            <small>Slokas</small>
                        </div>
                    </div>

                    <div class="hero-stat">
                        <div class="stat-icon">♧</div>

                        <div>
                            <strong>Life</strong>
                            <small>Solutions</small>
                        </div>
                    </div>

                    <div class="hero-stat">
                        <div class="stat-icon">◈</div>

                        <div>
                            <strong>Multiple</strong>
                            <small>Languages</small>
                        </div>
                    </div>

                    <div class="hero-stat">
                        <div class="stat-icon">✦</div>

                        <div>
                            <strong>A More</strong>
                            <small>Peaceful You</small>
                        </div>
                    </div>
                </div>

                <div class="hero-quote">
                    <!-- <span>“</span> -->

                    <p>
                        " Whenever you are confused,<br />
                        turn within. The Gita is the light<br />
                        that guides you " .
                    </p>

                    <small>— SRI SWAMI MUKUNDANANDA JI</small>
                </div>
            </div>

            <div class="hero-side-content">
                <div class="hero-journey-list">
                    <span>Read</span>
                    <span>Understand</span>
                    <span>Reflect</span>
                    <span>Apply</span>
                    <span>Transform</span>
                </div>
            </div>
        </div>

        <!-- <div class="hero-scroll-indicator">
            <span>↓</span>
            <small>SCROLL TO EXPLORE</small>
        </div> -->

        <div class="hero-slide-indicators">
            <button
                v-for="(image, index) in backgroundImages"
                :key="index"
                :class="{ active: currentImageIndex === index }"
                @click="currentImageIndex = index"
                :aria-label="`Show slide ${index + 1}`"
            ></button>
        </div>
    </section>
</template>