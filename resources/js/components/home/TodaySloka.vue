<script setup>
const sloka = {
    chapter: 'Chapter 2',
    verse: 'Verse 47',
    sanskrit:
        'कर्मण्येवाधिकारस्ते मा फलेषु कदाचन ।\nमा कर्मफलहेतुर्भूर्मा ते सङ्गोऽस्त्वकर्मणि ॥',
    transliteration:
        'Karmaṇy evādhikāras te mā phaleṣu kadācana',
    meaning:
        'You have a right to perform your prescribed duties, but you are not entitled to the fruits of your actions.',
    lesson:
        'Focus on sincere effort rather than becoming anxious about the result.'
};
</script>

<template>
    <section class="today-sloka-section">
        <div class="today-sloka-container">
            <div class="today-sloka-heading">
                <div>
                    <p class="section-eyebrow">
                        YOUR DAILY MOMENT OF WISDOM
                    </p>

                    <h2>
                        Today’s <span>Sloka</span>
                    </h2>
                </div>

                <p class="today-date">
                    Tuesday, September 11, 2026
                </p>
            </div>

            <div class="today-sloka-card">
                <div class="sloka-card-decoration decoration-top">
                    ✦
                </div>

                <div class="sloka-card-left">
                    <div class="sloka-meta">
                        <span>{{ sloka.chapter }}</span>
                        <i></i>
                        <span>{{ sloka.verse }}</span>
                    </div>

                    <div class="sanskrit-text">
                        <p
                            v-for="line in sloka.sanskrit.split('\n')"
                            :key="line"
                        >
                            {{ line }}
                        </p>
                    </div>

                    <p class="sloka-transliteration">
                        {{ sloka.transliteration }}
                    </p>

                    <div class="sloka-actions">
                        <router-link
                            to="/slokas/2/47"
                            class="sloka-primary-button"
                        >
                            Read Full Sloka
                            <span>→</span>
                        </router-link>

                        <button class="sloka-audio-button">
                            <span>◉</span>
                            Listen
                        </button>
                    </div>
                </div>

                <div class="sloka-card-divider"></div>

                <div class="sloka-card-right">
                    <p class="meaning-label">
                        SIMPLE MEANING
                    </p>

                    <p class="sloka-meaning">
                        “{{ sloka.meaning }}”
                    </p>

                    <div class="sloka-lesson-box">
                        <div class="lesson-icon">
                            ✦
                        </div>

                        <div>
                            <p class="lesson-label">
                                LIFE LESSON
                            </p>

                            <p class="lesson-text">
                                {{ sloka.lesson }}
                            </p>
                        </div>
                    </div>

                    <button class="save-sloka-button">
                        ♡
                        Save to My Wisdom
                    </button>
                </div>

                <div class="sloka-card-decoration decoration-bottom">
                    ✦
                </div>
            </div>
        </div>
    </section>
</template>