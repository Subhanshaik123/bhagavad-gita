<template>
    <section class="life-wisdom-section" id="wisdom-topics">
        <div class="life-wisdom-container">

            <!-- Section Header -->
            <div class="life-wisdom-header">
                <div>
                    <span class="life-wisdom-eyebrow">
                        Practical Spiritual Guidance
                    </span>

                    <h2>
                        Find Wisdom for
                        <span>Your Life</span>
                    </h2>
                </div>

                <p>
                    Real life questions. Timeless answers.
                </p>
            </div>

            <!-- Topic Grid -->
            <div class="wisdom-topic-grid">
                <a
                    v-for="topic in topics"
                    :key="topic.id"
                    href="#wisdom-topics"
                    class="wisdom-topic-card"
                >
                    <div
                        class="wisdom-topic-icon"
                        :class="`topic-${topic.color}`"
                    >
                        {{ topic.icon }}
                    </div>

                    <div class="wisdom-topic-content">
                        <h3>{{ topic.title }}</h3>
                        <p>{{ topic.description }}</p>
                    </div>
                </a>
            </div>

            <!-- Bottom Action -->
            <div class="wisdom-bottom-action">
                <a href="#wisdom-topics" class="explore-topics-link">
                    Explore All Topics
                    <span>→</span>
                </a>
            </div>

        </div>
    </section>
</template>

<script setup>
const topics = [
    {
        id: 1,
        icon: '✾',
        title: 'Stress & Anxiety',
        description: 'Find inner peace',
        color: 'blue',
    },
    {
        id: 2,
        icon: '▲',
        title: 'Self-Confidence',
        description: 'Build a stronger you',
        color: 'teal',
    },
    {
        id: 3,
        icon: '♥',
        title: 'Relationships',
        description: 'Create deeper bonds',
        color: 'red',
    },
    {
        id: 4,
        icon: '✚',
        title: 'Decision Making',
        description: 'Find clarity',
        color: 'green',
    },
    {
        id: 5,
        icon: '↗',
        title: 'Failure & Setbacks',
        description: 'Rise with wisdom',
        color: 'orange',
    },
    {
        id: 6,
        icon: '☀',
        title: 'Purpose & Meaning',
        description: 'Discover your path',
        color: 'gold',
    },
    {
        id: 7,
        icon: '♨',
        title: 'Anger',
        description: 'Respond, don’t react',
        color: 'fire',
    },
    {
        id: 8,
        icon: '♜',
        title: 'Fear',
        description: 'Find courage',
        color: 'shield',
    },
    {
        id: 9,
        icon: '❧',
        title: 'Discipline',
        description: 'Build better habits',
        color: 'leaf',
    },
    {
        id: 10,
        icon: '✤',
        title: 'Confusion',
        description: 'Gain perspective',
        color: 'purple',
    },
    {
        id: 11,
        icon: '▮',
        title: 'Material Success',
        description: 'Balance and grow',
        color: 'brown',
    },
    {
        id: 12,
        icon: '♟',
        title: 'Inner Peace',
        description: 'Experience stillness',
        color: 'pink',
    },
];
</script>

<style scoped>
/* =========================================
   LIFE WISDOM SECTION
========================================= */

.life-wisdom-section {
    position: relative;
    padding: 70px 0 32px;
    background:
        radial-gradient(
            circle at 10% 80%,
            rgba(191, 146, 65, 0.08),
            transparent 28%
        ),
        #f8f3e9;
    overflow: hidden;
}

.life-wisdom-section::before {
    content: '';
    position: absolute;
    left: -80px;
    bottom: -110px;
    width: 250px;
    height: 250px;
    border: 1px solid rgba(181, 132, 43, 0.14);
    border-radius: 50%;
    box-shadow:
        0 0 0 22px rgba(181, 132, 43, 0.025),
        0 0 0 45px rgba(181, 132, 43, 0.025),
        0 0 0 68px rgba(181, 132, 43, 0.025);
    pointer-events: none;
}

.life-wisdom-container {
    position: relative;
    z-index: 1;
    width: min(1180px, calc(100% - 48px));
    margin: 0 auto;
}

/* =========================================
   HEADER
========================================= */

.life-wisdom-header {
    display: flex;
    align-items: flex-end;
    justify-content: space-between;
    gap: 30px;
    margin-bottom: 28px;
}

.life-wisdom-eyebrow {
    display: block;
    margin-bottom: 8px;
    color: #a97928;
    font-size: 0.72rem;
    font-weight: 800;
    letter-spacing: 0.18em;
    text-transform: uppercase;
}

.life-wisdom-header h2 {
    margin: 0;
    color: #1b2942;
    font-family: 'Playfair Display', Georgia, serif;
    font-size: clamp(1.9rem, 3vw, 2.75rem);
    font-weight: 600;
    line-height: 1.2;
}

.life-wisdom-header h2 span {
    color: #a97928;
}

.life-wisdom-header > p {
    margin: 0 0 8px;
    color: #777168;
    font-family: 'Playfair Display', Georgia, serif;
    font-size: 0.92rem;
    white-space: nowrap;
}

/* =========================================
   TOPIC GRID
========================================= */

.wisdom-topic-grid {
    display: grid;
    grid-template-columns: repeat(6, 1fr);
    gap: 8px;
}

.wisdom-topic-card {
    display: flex;
    min-height: 126px;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    padding: 12px 8px;
    border: 1px solid rgba(164, 126, 62, 0.16);
    border-radius: 8px;
    background: rgba(255, 252, 245, 0.55);
    box-shadow: 0 4px 13px rgba(80, 61, 29, 0.025);
    text-align: center;
    text-decoration: none;
    transition:
        transform 0.3s ease,
        border-color 0.3s ease,
        background 0.3s ease,
        box-shadow 0.3s ease;
}

.wisdom-topic-card:hover {
    transform: translateY(-4px);
    border-color: rgba(164, 126, 62, 0.35);
    background: #fffdf8;
    box-shadow: 0 12px 25px rgba(80, 61, 29, 0.08);
}

/* =========================================
   TOPIC ICONS
========================================= */

.wisdom-topic-icon {
    display: flex;
    align-items: center;
    justify-content: center;
    width: 47px;
    height: 47px;
    margin-bottom: 11px;
    border-radius: 50%;
    font-size: 1.55rem;
    font-weight: 500;
    line-height: 1;
}

.topic-blue {
    background: #e5edf6;
    color: #5c8fc5;
}

.topic-teal {
    background: #e3eeee;
    color: #518a8e;
}

.topic-red {
    background: #fae5e2;
    color: #dc746c;
}

.topic-green {
    background: #e5efe5;
    color: #5d9a79;
}

.topic-orange {
    background: #fbeedc;
    color: #d99338;
}

.topic-gold {
    background: #fbead1;
    color: #d88d28;
}

.topic-fire {
    background: #fae6df;
    color: #d66b4c;
}

.topic-shield {
    background: #e4edf8;
    color: #5c82b7;
}

.topic-leaf {
    background: #e7f0e2;
    color: #63916a;
}

.topic-purple {
    background: #eee6f3;
    color: #8c6ba9;
}

.topic-brown {
    background: #f1e7da;
    color: #a7794d;
}

.topic-pink {
    background: #f8e2e2;
    color: #b86b6b;
}

/* =========================================
   TOPIC CONTENT
========================================= */

.wisdom-topic-content h3 {
    margin: 0 0 5px;
    color: #282b32;
    font-family: 'Playfair Display', Georgia, serif;
    font-size: 0.85rem;
    font-weight: 700;
    line-height: 1.25;
}

.wisdom-topic-content p {
    margin: 0;
    color: #77736c;
    font-family: 'Playfair Display', Georgia, serif;
    font-size: 0.7rem;
    line-height: 1.25;
}

/* =========================================
   BOTTOM ACTION
========================================= */

.wisdom-bottom-action {
    display: flex;
    justify-content: flex-end;
    margin-top: 8px;
}

.explore-topics-link {
    display: inline-flex;
    align-items: center;
    gap: 10px;
    color: #333b45;
    font-size: 0.75rem;
    font-weight: 800;
    text-decoration: none;
    transition:
        color 0.25s ease,
        gap 0.25s ease;
}

.explore-topics-link span {
    font-size: 1.05rem;
}

.explore-topics-link:hover {
    gap: 15px;
    color: #a97928;
}

/* =========================================
   RESPONSIVE DESIGN
========================================= */

@media (max-width: 1050px) {
    .wisdom-topic-grid {
        grid-template-columns: repeat(4, 1fr);
        gap: 10px;
    }
}

@media (max-width: 700px) {
    .life-wisdom-section {
        padding: 60px 0 28px;
    }

    .life-wisdom-container {
        width: calc(100% - 32px);
    }

    .life-wisdom-header {
        align-items: flex-start;
        flex-direction: column;
        gap: 12px;
    }

    .life-wisdom-header > p {
        margin: 0;
        white-space: normal;
    }

    .wisdom-topic-grid {
        grid-template-columns: repeat(3, 1fr);
        gap: 8px;
    }

    .wisdom-topic-card {
        min-height: 120px;
        padding: 10px 5px;
    }

    .wisdom-topic-icon {
        width: 40px;
        height: 40px;
        font-size: 1.3rem;
    }

    .wisdom-topic-content h3 {
        font-size: 0.76rem;
    }

    .wisdom-topic-content p {
        font-size: 0.62rem;
    }
}

@media (max-width: 430px) {
    .wisdom-topic-grid {
        grid-template-columns: repeat(2, 1fr);
        gap: 10px;
    }

    .wisdom-topic-card {
        min-height: 125px;
    }
}
</style>