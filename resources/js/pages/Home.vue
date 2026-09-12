<template>
    <MainLayout>
        <div class="page-content">
            <HeroSection />
            <TodaySloka />
            <ChaptersSection />
            <!-- <FeaturedSlokas /> -->
            <LifeWisdomSection />
            <SpiritualPracticeSection />
            <WisdomDimensionsSection />
            <JourneyCtaSection />
        </div>
    </MainLayout>
</template>


<script setup>
import JourneyCtaSection from '../components/home/JourneyCtaSection.vue'
import MainLayout from '../layouts/MainLayout.vue';
import HeroSection from '../components/home/HeroSection.vue';
import TodaySloka from '../components/home/TodaySloka.vue';
import ChaptersSection from '../components/home/ChaptersSection.vue';
// import FeaturedSlokas from '../components/home/FeaturedSlokas.vue';
import LifeWisdomSection from '../components/home/LifeWisdomSection.vue';
import SpiritualPracticeSection from '../components/home/SpiritualPracticeSection.vue';
import WisdomDimensionsSection from '../components/home/WisdomDimensionsSection.vue';
</script>