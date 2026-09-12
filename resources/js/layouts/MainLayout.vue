<template>
    <div class="main-layout">
        <Navbar />

        <main>
            <slot />
        </main>

        <Footer />
    </div>
</template>

<script setup>
import Navbar from '../components/navigation/Navbar.vue'
import Footer from '../components/navigation/Footer.vue'
</script>