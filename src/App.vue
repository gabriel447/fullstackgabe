<template>
  <div id="app-root">
    <HeroSection />
    <MethodSection />
    <SkillsSection />
    <ExperienceSection />
    <TestimonialSection />
    <CtaSection />
  </div>
</template>

<script setup>
import HeroSection from './components/HeroSection.vue'
import MethodSection from './components/MethodSection.vue'
import SkillsSection from './components/SkillsSection.vue'
import ExperienceSection from './components/ExperienceSection.vue'
import TestimonialSection from './components/TestimonialSection.vue'
import CtaSection from './components/CtaSection.vue'
</script>

<style>
#app-root {
  min-height: 100vh;
}
</style>
