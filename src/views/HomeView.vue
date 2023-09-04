<script setup>
import HeaderSection from "@/components/HeaderSection.vue";
import FooterSection from "@/components/FooterSection.vue";
import IntroSection from "@/components/IntroSection.vue";
import SkillSection from "@/components/SkillSection.vue";
import SiteSection from "@/components/SiteSection.vue";
import PortfolioSection from "@/components/PortfolioSection.vue";
import ContactSection from "@/components/ContactSection.vue";
import SkipSection from "@/components/SkipSection.vue";
</script>

<template>
    <SkipSection />
    <HeaderSection />
    <main id="main" role="main">
        <IntroSection />
        <SkillSection />
        <SiteSection />
        <PortfolioSection />
        <ContactSection />
    </main>
    <FooterSection />
</template>