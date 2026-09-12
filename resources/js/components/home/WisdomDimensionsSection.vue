<template>
    <section class="wisdom-dimensions-section" id="wisdom-dimensions">
        <div class="wisdom-dimensions-container">

            <!-- Section Header -->
            <div class="dimensions-header">
                <h2>
                    Every Sloka. Six Dimensions of Wisdom.
                </h2>

                <p>
                    Not just knowledge, but a complete understanding for real life.
                </p>
            </div>

            <!-- Main Layout -->
            <div class="dimensions-layout">

                <!-- Six Dimensions -->
                <div class="dimensions-list">

                    <article
                        v-for="(dimension, index) in dimensions"
                        :key="dimension.id"
                        class="dimension-item"
                        :class="`dimension-card-${dimension.color}`"
                        @mousemove="handleMouseMove"
                        @mouseleave="handleMouseLeave"
                    >
                        <!-- Cursor Glow -->
                        <div class="dimension-cursor-glow"></div>

                        <!-- Connecting Line -->
                        <div
                            v-if="index < dimensions.length - 1"
                            class="dimension-connector"
                        ></div>

                        <!-- Icon -->
                        <div
                            class="dimension-icon"
                            :class="`dimension-${dimension.color}`"
                        >
                            <span>{{ dimension.icon }}</span>
                        </div>

                        <!-- Number -->
                        <span class="dimension-number">
                            {{ String(dimension.id).padStart(2, '0') }}
                        </span>

                        <!-- Title -->
                        <h3>
                            {{ dimension.title }}
                        </h3>

                        <!-- Question -->
                        <p class="dimension-question">
                            {{ dimension.question }}
                        </p>

                        <!-- Description -->
                        <p class="dimension-description">
                            {{ dimension.description }}
                        </p>
                    </article>

                </div>

                <!-- Right Side Message -->
                <div class="dimensions-side-message">
                    <span class="side-message-small">
                        From
                    </span>

                    <strong>
                        Knowledge
                    </strong>

                    <span class="side-message-small">
                        to
                    </span>

                    <strong>
                        Action.
                    </strong>

                    <span class="side-message-small">
                        Better For
                    </span>

                    <strong>
                        You.
                    </strong>

                    <div class="side-message-divider">
                        <span>✦</span>
                    </div>
                </div>

            </div>

        </div>
    </section>
</template>

<script setup>
const handleMouseMove = (event) => {
    const card = event.currentTarget;
    const rect = card.getBoundingClientRect();

    const x = event.clientX - rect.left;
    const y = event.clientY - rect.top;

    card.style.setProperty('--mouse-x', `${x}px`);
    card.style.setProperty('--mouse-y', `${y}px`);
    card.style.setProperty('--glow-opacity', '1');
};

const handleMouseLeave = (event) => {
    const card = event.currentTarget;

    card.style.setProperty('--glow-opacity', '0');
};

const dimensions = [
    {
        id: 1,
        icon: '▣',
        title: 'The Sloka',
        question: 'What does Krishna say?',
        description: 'Understand the original teaching.',
        color: 'gold',
    },
    {
        id: 2,
        icon: '♧',
        title: 'Simple Meaning',
        question: 'What does it mean?',
        description: 'Understand the message clearly.',
        color: 'teal',
    },
    {
        id: 3,
        icon: '❧',
        title: 'Life Lesson',
        question: 'What can I learn?',
        description: 'Discover the wisdom within.',
        color: 'blue',
    },
    {
        id: 4,
        icon: '♟',
        title: 'Life Problem',
        question: 'Where does this apply in my life?',
        description: 'Connect wisdom with real challenges.',
        color: 'purple',
    },
    {
        id: 5,
        icon: '⚙',
        title: 'Practical Solution',
        question: 'What should I do?',
        description: 'Turn understanding into action.',
        color: 'orange',
    },
    {
        id: 6,
        icon: '▶',
        title: 'Guidance',
        question: 'Go deeper with Swami Mukundananda Ji',
        description: 'Listen, reflect, and grow.',
        color: 'red',
    },
];
</script>

<style scoped>
/* =========================================
   MAIN SECTION
========================================= */

.wisdom-dimensions-section {
    position: relative;
    padding: 62px 0 55px;
    background:
        linear-gradient(
            90deg,
            rgba(4, 18, 29, 0.97),
            rgba(8, 25, 37, 0.98),
            rgba(4, 18, 29, 0.97)
        );
    overflow: hidden;
}

.wisdom-dimensions-section::before {
    content: '';
    position: absolute;
    inset: 0;
    background:
        radial-gradient(
            circle at 15% 80%,
            rgba(41, 96, 115, 0.15),
            transparent 35%
        ),
        radial-gradient(
            circle at 80% 20%,
            rgba(177, 124, 42, 0.08),
            transparent 30%
        );
    pointer-events: none;
}

.wisdom-dimensions-section::after {
    content: 'ॐ';
    position: absolute;
    right: 5%;
    bottom: -150px;
    color: rgba(255, 255, 255, 0.025);
    font-family: Georgia, serif;
    font-size: 22rem;
    pointer-events: none;
}

.wisdom-dimensions-container {
    position: relative;
    z-index: 1;
    width: min(1180px, calc(100% - 48px));
    margin: 0 auto;
}

/* =========================================
   HEADER
========================================= */

.dimensions-header {
    margin-bottom: 38px;
    text-align: center;
}

.dimensions-header h2 {
    margin: 0 0 8px;
    color: #f8f1df;
    font-family: 'Playfair Display', Georgia, serif;
    font-size: clamp(1.8rem, 3vw, 2.35rem);
    font-weight: 600;
    letter-spacing: 0.01em;
    line-height: 1.2;
}

.dimensions-header p {
    margin: 0;
    color: rgba(248, 241, 223, 0.65);
    font-family: 'Playfair Display', Georgia, serif;
    font-size: 0.82rem;
}

/* =========================================
   LAYOUT
========================================= */

.dimensions-layout {
    display: flex;
    align-items: flex-start;
    gap: 35px;
}

.dimensions-list {
    position: relative;
    display: grid;
    flex: 1;
    grid-template-columns: repeat(6, 1fr);
    gap: 12px;
}

/* =========================================
   DIMENSION ITEM
========================================= */

.dimension-item {
    --mouse-x: 50%;
    --mouse-y: 50%;
    --glow-opacity: 0;

    position: relative;
    isolation: isolate;
    display: flex;
    flex-direction: column;
    align-items: center;
    min-width: 0;
    padding: 12px 8px 16px;
    border: 1px solid transparent;
    border-radius: 18px;
    text-align: center;
    transition:
        transform 0.35s ease,
        border-color 0.35s ease,
        background 0.35s ease;
}

/* =========================================
   CURSOR FOLLOWING GLOW
========================================= */

.dimension-cursor-glow {
    position: absolute;
    inset: 0;
    z-index: -2;
    border-radius: inherit;
    background: radial-gradient(
        135px circle at var(--mouse-x) var(--mouse-y),
        var(--glow-color),
        transparent 72%
    );
    opacity: var(--glow-opacity);
    transition: opacity 0.25s ease;
    pointer-events: none;
}

.dimension-item::before {
    content: '';
    position: absolute;
    inset: 1px;
    z-index: -1;
    border-radius: inherit;
    background: rgba(8, 27, 39, 0.45);
    opacity: var(--glow-opacity);
    transition: opacity 0.25s ease;
    pointer-events: none;
}

.dimension-item:hover {
    transform: translateY(-6px);
    border-color: var(--glow-border);
}

/* Individual Glow Colors */

.dimension-card-gold {
    --glow-color: rgba(241, 189, 85, 0.36);
    --glow-border: rgba(241, 189, 85, 0.55);
}

.dimension-card-teal {
    --glow-color: rgba(114, 224, 199, 0.36);
    --glow-border: rgba(114, 224, 199, 0.55);
}

.dimension-card-blue {
    --glow-color: rgba(120, 206, 250, 0.36);
    --glow-border: rgba(120, 206, 250, 0.55);
}

.dimension-card-purple {
    --glow-color: rgba(215, 151, 255, 0.36);
    --glow-border: rgba(215, 151, 255, 0.55);
}

.dimension-card-orange {
    --glow-color: rgba(255, 198, 109, 0.36);
    --glow-border: rgba(255, 198, 109, 0.55);
}

.dimension-card-red {
    --glow-color: rgba(255, 146, 137, 0.36);
    --glow-border: rgba(255, 146, 137, 0.55);
}

/* =========================================
   CONNECTING LINE
========================================= */

.dimension-connector {
    position: absolute;
    top: 36px;
    left: calc(50% + 25px);
    width: calc(100% - 1px);
    height: 1px;
    z-index: -1;
    background: linear-gradient(
        to right,
        rgba(214, 173, 91, 0.5),
        rgba(214, 173, 91, 0.15)
    );
    pointer-events: none;
}

/* =========================================
   ICON
========================================= */

.dimension-icon {
    position: relative;
    z-index: 2;
    display: flex;
    align-items: center;
    justify-content: center;
    width: 48px;
    height: 48px;
    margin-bottom: 13px;
    border: 1px solid;
    border-radius: 50%;
    background: rgba(8, 27, 39, 0.96);
    box-shadow:
        0 0 16px rgba(255, 255, 255, 0.05),
        inset 0 0 12px rgba(255, 255, 255, 0.04);
    transition:
        transform 0.35s ease,
        box-shadow 0.35s ease;
}

.dimension-item:hover .dimension-icon {
    transform: scale(1.12);
}

.dimension-icon span {
    font-size: 1.35rem;
    line-height: 1;
}

/* =========================================
   ICON COLORS
========================================= */

.dimension-gold {
    border-color: #dba944;
    color: #f1bd55;
    box-shadow:
        0 0 17px rgba(219, 169, 68, 0.25),
        inset 0 0 12px rgba(219, 169, 68, 0.08);
}

.dimension-teal {
    border-color: #47c8b1;
    color: #72e0c7;
    box-shadow:
        0 0 17px rgba(71, 200, 177, 0.25),
        inset 0 0 12px rgba(71, 200, 177, 0.08);
}

.dimension-blue {
    border-color: #55b8ed;
    color: #78cefa;
    box-shadow:
        0 0 17px rgba(85, 184, 237, 0.25),
        inset 0 0 12px rgba(85, 184, 237, 0.08);
}

.dimension-purple {
    border-color: #bb70ed;
    color: #d797ff;
    box-shadow:
        0 0 17px rgba(187, 112, 237, 0.25),
        inset 0 0 12px rgba(187, 112, 237, 0.08);
}

.dimension-orange {
    border-color: #e8a94e;
    color: #ffc66d;
    box-shadow:
        0 0 17px rgba(232, 169, 78, 0.25),
        inset 0 0 12px rgba(232, 169, 78, 0.08);
}

.dimension-red {
    border-color: #ee6b64;
    color: #ff9289;
    box-shadow:
        0 0 17px rgba(238, 107, 100, 0.25),
        inset 0 0 12px rgba(238, 107, 100, 0.08);
}

/* =========================================
   TEXT
========================================= */

.dimension-number {
    position: relative;
    z-index: 2;
    margin-bottom: 8px;
    color: #f3d28a;
    font-size: 0.68rem;
    font-weight: 800;
    letter-spacing: 0.12em;
}

.dimension-item h3 {
    position: relative;
    z-index: 2;
    min-height: 31px;
    margin: 0 0 7px;
    color: #f9f1df;
    font-family: 'Playfair Display', Georgia, serif;
    font-size: 0.82rem;
    font-weight: 600;
    line-height: 1.25;
}

.dimension-question {
    position: relative;
    z-index: 2;
    min-height: 34px;
    margin: 0;
    color: rgba(249, 241, 223, 0.78);
    font-family: 'Playfair Display', Georgia, serif;
    font-size: 0.69rem;
    line-height: 1.4;
}

.dimension-description {
    position: relative;
    z-index: 2;
    display: none;
    margin: 8px 0 0;
    color: rgba(249, 241, 223, 0.48);
    font-size: 0.65rem;
    line-height: 1.4;
}

/* =========================================
   SIDE MESSAGE
========================================= */

.dimensions-side-message {
    display: flex;
    flex: 0 0 125px;
    min-height: 155px;
    flex-direction: column;
    justify-content: center;
    padding-left: 15px;
    border-left: 1px solid rgba(214, 173, 91, 0.25);
    color: #e4b85e;
    font-family: 'Playfair Display', Georgia, serif;
    font-size: 1rem;
    font-style: italic;
    line-height: 1.25;
}

.side-message-small {
    color: #e4b85e;
    font-size: 0.86rem;
}

.dimensions-side-message strong {
    color: #e8bc61;
    font-size: 1.05rem;
    font-weight: 600;
}

.side-message-divider {
    display: flex;
    align-items: center;
    gap: 7px;
    margin-top: 16px;
    color: #b8842d;
}

.side-message-divider::before,
.side-message-divider::after {
    content: '';
    width: 24px;
    height: 1px;
    background: #b8842d;
}

.side-message-divider span {
    font-size: 0.65rem;
}

/* =========================================
   RESPONSIVE DESIGN
========================================= */

@media (max-width: 1050px) {
    .dimensions-layout {
        gap: 20px;
    }

    .dimensions-side-message {
        flex-basis: 105px;
        padding-left: 12px;
    }

    .dimensions-side-message strong {
        font-size: 0.92rem;
    }

    .side-message-small {
        font-size: 0.76rem;
    }

    .dimension-item h3 {
        font-size: 0.75rem;
    }

    .dimension-question {
        font-size: 0.63rem;
    }
}

@media (max-width: 800px) {
    .wisdom-dimensions-section {
        padding: 70px 0 55px;
    }

    .dimensions-layout {
        display: block;
    }

    .dimensions-list {
        grid-template-columns: repeat(3, 1fr);
        row-gap: 35px;
    }

    .dimension-connector {
        display: none;
    }

    .dimensions-side-message {
        min-height: auto;
        margin: 45px auto 0;
        padding: 20px 0 0;
        border-top: 1px solid rgba(214, 173, 91, 0.25);
        border-left: none;
        text-align: center;
    }

    .side-message-divider {
        justify-content: center;
    }
}

@media (max-width: 500px) {
    .wisdom-dimensions-container {
        width: calc(100% - 32px);
    }

    .dimensions-header h2 {
        font-size: 1.7rem;
    }

    .dimensions-header p {
        font-size: 0.75rem;
        line-height: 1.5;
    }

    .dimensions-list {
        grid-template-columns: repeat(2, 1fr);
        gap: 30px 15px;
    }

    .dimension-icon {
        width: 45px;
        height: 45px;
    }

    .dimension-item h3 {
        font-size: 0.82rem;
    }

    .dimension-question {
        font-size: 0.68rem;
    }

    .dimension-number {
        font-size: 0.65rem;
    }
}
</style>