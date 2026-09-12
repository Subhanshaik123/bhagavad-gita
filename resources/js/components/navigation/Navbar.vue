<script setup>
import { ref } from 'vue';

const mobileMenuOpen = ref(false);
const languageOpen = ref(false);
</script>


<template>
    <header class="premium-navbar">

        <div class="navbar-container">

            <!-- Brand -->
            <router-link to="/" class="premium-brand">
                <div class="brand-lotus">
                    <span>✦</span>
                </div>

                <div class="brand-details">
                    <strong>BHAGAVAD GITA</strong>
                    <small>Timeless Wisdom • A Better You</small>
                </div>
            </router-link>


            <!-- Desktop Navigation -->
            <nav class="premium-nav-links">
                <router-link to="/" class="active">
                    Home
                </router-link>

                <router-link to="/chapters">
                    Chapters
                </router-link>

                <router-link to="/wisdom">
                    Wisdom for Life
                </router-link>

                <router-link to="/daily-sloka">
                    Daily Sloka
                </router-link>

                <router-link to="/resources">
                    Resources
                </router-link>

                <router-link to="/about">
                    About
                </router-link>
            </nav>


            <!-- Navbar Actions -->
            <div class="premium-navbar-actions">

                <!-- Search -->
                <button class="nav-search-button">
                    <span>⌕</span>
                    <small>Search...</small>
                </button>


                <!-- Language -->
                <div class="language-wrapper">

                    <button
                        class="language-button"
                        @click="languageOpen = !languageOpen"
                    >
                        <span>🌐</span>
                        <span>Languages</span>
                        <span class="language-arrow">⌄</span>
                    </button>

                    <div
                        v-if="languageOpen"
                        class="language-dropdown"
                    >
                        <button>English</button>
                        <button>हिन्दी</button>
                        <button>తెలుగు</button>
                        <button>தமிழ்</button>
                        <button>ಕನ್ನಡ</button>
                        <button> Español</button>

                        <div class="dropdown-divider"></div>

                        <button>More Languages →</button>
                    </div>

                </div>


                <!-- Theme -->
                <button class="theme-toggle">
                    ☼
                </button>


                <!-- Sign In -->
                <router-link
                    to="/signin"
                    class="nav-signin-button"
                >
                    Sign In
                </router-link>


                <!-- Mobile Menu Button -->
                <button
                    class="mobile-menu-toggle"
                    @click="mobileMenuOpen = !mobileMenuOpen"
                >
                    ☰
                </button>

            </div>

        </div>


        <!-- Mobile Navigation -->
        <div
            v-if="mobileMenuOpen"
            class="mobile-premium-menu"
        >
            <router-link
                to="/"
                @click="mobileMenuOpen = false"
            >
                Home
            </router-link>

            <router-link
                to="/chapters"
                @click="mobileMenuOpen = false"
            >
                Chapters
            </router-link>

            <router-link
                to="/wisdom"
                @click="mobileMenuOpen = false"
            >
                Wisdom for Life
            </router-link>

            <router-link
                to="/daily-sloka"
                @click="mobileMenuOpen = false"
            >
                Daily Sloka
            </router-link>

            <router-link
                to="/resources"
                @click="mobileMenuOpen = false"
            >
                Resources
            </router-link>

            <router-link
                to="/about"
                @click="mobileMenuOpen = false"
            >
                About
            </router-link>
        </div>

    </header>
</template>


<style scoped>

/* =========================================
   MAIN NAVBAR
========================================= */

.premium-navbar {
    position: fixed;
    top: 0;
    left: 0;

    width: 100%;
    height: 80px;

    z-index: 9999;

    background:
        linear-gradient(
            90deg,
            rgba(6, 24, 34, 0.97),
            rgba(11, 30, 39, 0.94),
            rgba(8, 24, 34, 0.97)
        );

    backdrop-filter: blur(16px);
    -webkit-backdrop-filter: blur(16px);

    border-bottom: 1px solid rgba(255, 255, 255, 0.12);

    box-shadow:
        0 5px 25px rgba(0, 0, 0, 0.12);

    transition:
        background 0.3s ease,
        box-shadow 0.3s ease;
}


/* =========================================
   NAVBAR CONTAINER
========================================= */

.navbar-container {
    width: min(1280px, 94%);
    height: 100%;

    margin: 0 auto;

    display: flex;
    align-items: center;
    justify-content: space-between;

    gap: 30px;
}


/* =========================================
   BRAND
========================================= */

.premium-brand {
    display: flex;
    align-items: center;

    gap: 12px;

    flex-shrink: 0;

    color: #f5ead4;
    text-decoration: none;
}

.brand-lotus {
    width: 43px;
    height: 43px;

    display: flex;
    align-items: center;
    justify-content: center;

    border: 1px solid #bd852d;
    border-radius: 50%;

    color: #e5a63c;

    font-size: 24px;

    box-shadow:
        0 0 15px rgba(214, 151, 44, 0.08);

    transition:
        transform 0.3s ease,
        background 0.3s ease,
        box-shadow 0.3s ease;
}

.premium-brand:hover .brand-lotus {
    transform: rotate(12deg) scale(1.05);

    background: rgba(209, 148, 46, 0.1);

    box-shadow:
        0 0 20px rgba(214, 151, 44, 0.25);
}

.brand-details {
    display: flex;
    flex-direction: column;

    gap: 3px;
}

.brand-details strong {
    color: #f3e5c7;

    font-family: Georgia, 'Times New Roman', serif;
    font-size: 16px;
    font-weight: 600;

    letter-spacing: 0.4px;
    line-height: 1;
}

.brand-details small {
    color: #b7a98d;

    font-family: Georgia, 'Times New Roman', serif;
    font-size: 8px;

    letter-spacing: 0.2px;
}


/* =========================================
   DESKTOP NAVIGATION
========================================= */

.premium-nav-links {
    display: flex;
    align-items: center;
    justify-content: center;

    /*
       Important:
       Do not add margin: 40px here.
       It pushes the active underline outside
       the Navbar and creates a gap.
    */

    gap: 28px;

    margin-left: auto;
    margin-right: auto;
}

.premium-nav-links a {
    position: relative;

    display: inline-flex;
    align-items: center;

    height: 80px;

    color: #d4c9b7;

    font-size: 15px;
    font-weight: 500;

    text-decoration: none;
    white-space: nowrap;

    transition:
        color 0.3s ease,
        transform 0.3s ease;
}


/* Active underline stays inside Navbar */

 .premium-nav-links a::after {
    content: '';

    position: absolute;

    left: 0;
    right: 0;

    bottom: 9px;

    height: 2px;

    background: #e4a63b;

    border-radius: 10px;

    transform: scaleX(0);
    transform-origin: center;

    transition:
        transform 0.3s ease,
        box-shadow 0.3s ease;
}

.premium-nav-links a:hover {
    color: #f1b94e;

    transform: translateY(-1px);
} 

.premium-nav-links a:hover::after,
.premium-nav-links a.router-link-active::after,
.premium-nav-links a.active::after {
    transform: scaleX(1);

    box-shadow:
        0 0 8px rgba(228, 166, 59, 0.45);
}

.premium-nav-links a.router-link-active,
.premium-nav-links a.active {
    color: #eeb34b;
}


/* =========================================
   NAVBAR ACTIONS
========================================= */

.premium-navbar-actions {
    display: flex;
    align-items: center;
    justify-content: flex-end;

    gap: 10px;

    flex-shrink: 0;
}


/* =========================================
   SEARCH BUTTON
========================================= */

.nav-search-button {
    display: flex;
    align-items: center;
    justify-content: center;

    gap: 8px;

    min-width: 105px;
    height: 40px;

    padding: 0 14px;

    border: 1px solid rgba(220, 205, 180, 0.35);
    border-radius: 24px;

    color: #e8ddc9;

    background: rgba(255, 255, 255, 0.035);

    cursor: pointer;

    transition:
        border-color 0.3s ease,
        background 0.3s ease,
        box-shadow 0.3s ease;
}

.nav-search-button span {
    font-size: 20px;
    line-height: 1;
}

.nav-search-button small {
    font-size: 10px;
}

.nav-search-button:hover {
    border-color: rgba(226, 169, 67, 0.7);

    background: rgba(226, 169, 67, 0.08);

    box-shadow:
        0 0 15px rgba(226, 169, 67, 0.08);
}


/* =========================================
   LANGUAGE BUTTON
========================================= */

.language-wrapper {
    position: relative;
}

.language-button {
    display: flex;
    align-items: center;
    justify-content: center;

    gap: 7px;

    height: 40px;
    padding: 0 13px;

    border: 1px solid rgba(220, 205, 180, 0.3);
    border-radius: 22px;

    color: #eee2cc;

    background: rgba(255, 255, 255, 0.035);

    font-size: 10px;

    cursor: pointer;

    transition:
        border-color 0.3s ease,
        background 0.3s ease;
}

.language-button:hover {
    border-color: rgba(226, 169, 67, 0.7);

    background: rgba(226, 169, 67, 0.08);
}

.language-arrow {
    font-size: 15px;
    margin-left: 2px;
}


/* =========================================
   LANGUAGE DROPDOWN
========================================= */

.language-dropdown {
    position: absolute;

    top: calc(100% + 12px);
    right: 0;

    width: 175px;

    padding: 8px;

    display: flex;
    flex-direction: column;

    gap: 3px;

    background: #102b35;

    border: 1px solid rgba(219, 161, 57, 0.35);
    border-radius: 12px;

    box-shadow:
        0 15px 35px rgba(0, 0, 0, 0.3);
}

.language-dropdown button {
    width: 100%;

    padding: 10px 12px;

    border: none;
    border-radius: 7px;

    color: #ded2be;
    background: transparent;

    font-size: 11px;
    text-align: left;

    cursor: pointer;

    transition:
        color 0.25s ease,
        background 0.25s ease;
}

.language-dropdown button:hover {
    color: #f1bd5a;

    background: rgba(231, 170, 63, 0.1);
}

.dropdown-divider {
    width: 100%;
    height: 1px;

    margin: 5px 0;

    background: rgba(255, 255, 255, 0.12);
}


/* =========================================
   THEME TOGGLE
========================================= */

.theme-toggle {
    width: 40px;
    height: 40px;

    display: flex;
    align-items: center;
    justify-content: center;

    border: 1px solid #a8792d;
    border-radius: 50%;

    color: #eab04a;

    background: rgba(255, 255, 255, 0.035);

    font-size: 22px;

    cursor: pointer;

    transition:
        transform 0.3s ease,
        background 0.3s ease,
        box-shadow 0.3s ease;
}

.theme-toggle:hover {
    transform: rotate(25deg);

    background: rgba(226, 169, 67, 0.1);

    box-shadow:
        0 0 18px rgba(226, 169, 67, 0.2);
}


/* =========================================
   SIGN IN BUTTON
========================================= */

.nav-signin-button {
    display: inline-flex;
    align-items: center;
    justify-content: center;

    min-width: 80px;
    height: 40px;

    padding: 0 20px;

    border-radius: 24px;

    color: #382716;

    background: linear-gradient(
        135deg,
        #f4c76d,
        #dca044
    );

    font-size: 10px;
    font-weight: 700;

    text-decoration: none;

    box-shadow:
        0 5px 15px rgba(225, 166, 65, 0.12);

    transition:
        transform 0.3s ease,
        box-shadow 0.3s ease,
        background 0.3s ease;
}

.nav-signin-button:hover {
    color: #2d2114;

    background: linear-gradient(
        135deg,
        #ffd98b,
        #e9ad4d
    );

    transform: translateY(-2px);

    box-shadow:
        0 8px 22px rgba(225, 166, 65, 0.25);
}


/* =========================================
   MOBILE MENU BUTTON
========================================= */

.mobile-menu-toggle {
    display: none;

    width: 40px;
    height: 40px;

    align-items: center;
    justify-content: center;

    border: 1px solid rgba(226, 169, 67, 0.45);
    border-radius: 8px;

    color: #eab04a;

    background: rgba(255, 255, 255, 0.04);

    font-size: 21px;

    cursor: pointer;
}


/* =========================================
   MOBILE MENU
========================================= */

.mobile-premium-menu {
    display: none;
}


/* =========================================
   TABLET
========================================= */

@media (max-width: 1150px) {
    .navbar-container {
        gap: 18px;
    }

    .premium-nav-links {
        gap: 18px;
    }

    .premium-nav-links a {
        font-size: 9px;
    }

    .brand-details strong {
        font-size: 14px;
    }

    .nav-search-button {
        min-width: 85px;
        padding: 0 10px;
    }

    .language-button {
        padding: 0 10px;
    }

    .nav-signin-button {
        min-width: 70px;
        padding: 0 15px;
    }
}


/* =========================================
   MOBILE
========================================= */

@media (max-width: 900px) {
    .premium-navbar {
        height: 72px;
    }

    .navbar-container {
        width: 92%;
    }

    .premium-nav-links {
        display: none;
    }

    .premium-navbar-actions {
        margin-left: auto;
    }

    .nav-search-button,
    .language-wrapper,
    .theme-toggle,
    .nav-signin-button {
        display: none;
    }

    .mobile-menu-toggle {
        display: flex;
    }

    .mobile-premium-menu {
        position: absolute;

        top: 72px;
        left: 0;

        width: 100%;

        padding: 15px;

        display: flex;
        flex-direction: column;

        gap: 5px;

        background: rgba(8, 25, 34, 0.98);

        border-top: 1px solid rgba(255, 255, 255, 0.08);
        border-bottom: 1px solid rgba(255, 255, 255, 0.12);

        box-shadow:
            0 15px 30px rgba(0, 0, 0, 0.25);
    }

    .mobile-premium-menu a {
        padding: 14px 18px;

        border-radius: 8px;

        color: #ded2be;

        font-size: 13px;

        text-decoration: none;

        transition:
            color 0.3s ease,
            background 0.3s ease;
    }

    .mobile-premium-menu a:hover,
    .mobile-premium-menu a.router-link-active {
        color: #f0b84e;

        background: rgba(226, 169, 67, 0.08);
    }

    .brand-lotus {
        width: 39px;
        height: 39px;

        font-size: 21px;
    }

    .brand-details strong {
        font-size: 14px;
    }

    .brand-details small {
        font-size: 7px;
    }
}


/* =========================================
   SMALL MOBILE
========================================= */

@media (max-width: 420px) {
    .brand-details strong {
        font-size: 12px;
    }

    .brand-details small {
        font-size: 6px;
    }

    .brand-lotus {
        width: 35px;
        height: 35px;

        font-size: 19px;
    }
}

</style>