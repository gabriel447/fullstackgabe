<template>
  <section id="skills" class="skills" ref="sectionRef">
    <div class="skills__header">
      <span class="skills__label-top">EXPERTISE</span>
      <h2 class="skills__title">My Skills</h2>
    </div>

    <div class="skills__grid">
      <div v-for="skill in skills" :key="skill.name" class="skills__item" :style="{ '--skill-color': skill.color }">
        <div class="skills__ring-wrap">
          <svg viewBox="0 0 120 120" class="skills__ring-svg" aria-hidden="true">
            <circle cx="60" cy="60" r="50" fill="none" stroke="#e0e0e0" stroke-width="4" />
            <circle
              cx="60" cy="60" r="50"
              fill="none"
              stroke-width="4"
              stroke-linecap="round"
              :stroke-dasharray="CIRC"
              :stroke-dashoffset="animated ? getOffset(skill.percent) : CIRC"
              transform="rotate(-90 60 60)"
              class="skills__ring-progress"
            />
          </svg>
          <div class="skills__circle-content">
            <img :src="skill.icon" :alt="skill.name" class="skills__icon" />
            <span class="skills__percent">{{ skill.percent }}%</span>
            <span class="skills__name">{{ skill.name }}</span>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
import { ref, onMounted } from 'vue'
import nodeIcon from '../assets/icons8-nodejs-144.png'
import jsIcon from '../assets/js.png'
import tsIcon from '../assets/ts-logo-128.png'
import reactNativeIcon from '../assets/react-native.png'

const CIRC = 2 * Math.PI * 50

const skills = [
  { name: 'NODE', icon: nodeIcon, percent: 69, color: '#539e43' },
  { name: 'JAVASCRIPT', icon: jsIcon, percent: 94, color: '#f0db4f' },
  { name: 'TYPESCRIPT', icon: tsIcon, percent: 77, color: '#3178c6' },
  { name: 'REACT NATIVE', icon: reactNativeIcon, percent: 85, color: '#61dafb' },
]

function getOffset(percent) {
  return CIRC * (1 - percent / 100)
}

const animated = ref(false)
const sectionRef = ref(null)

onMounted(() => {
  const observer = new IntersectionObserver(
    (entries) => {
      if (entries[0].isIntersecting) {
        animated.value = true
        observer.disconnect()
      }
    },
    { threshold: 0.25 }
  )
  if (sectionRef.value) observer.observe(sectionRef.value)
})
</script>

<style scoped>
.skills {
  padding: 8rem 5% 7rem;
  border-top: 1px solid var(--color-gray);
}

.skills__header {
  text-align: center;
  margin-bottom: 5rem;
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 0.8rem;
}

.skills__label-top {
  font-size: 0.65rem;
  font-weight: 700;
  letter-spacing: 0.2em;
  color: var(--color-gray-mid);
}

.skills__title {
  font-family: var(--font-serif);
  font-size: clamp(2.2rem, 4vw, 3.2rem);
  font-weight: 400;
}

.skills__grid {
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  gap: 2rem;
  max-width: 1000px;
  margin: 0 auto;
}

.skills__item {
  display: flex;
  justify-content: center;
}

.skills__ring-wrap {
  position: relative;
  width: clamp(160px, 16vw, 220px);
  height: clamp(160px, 16vw, 220px);
}

.skills__ring-svg {
  width: 100%;
  height: 100%;
}

.skills__ring-progress {
  stroke: #aaa;
  transition: stroke-dashoffset 1.4s cubic-bezier(0.4, 0, 0.2, 1), stroke 0.4s ease;
}

.skills__item:hover .skills__ring-progress {
  stroke: var(--skill-color);
}

.skills__circle-content {
  position: absolute;
  inset: 0;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  gap: 0.6rem;
}

.skills__icon {
  width: clamp(36px, 4vw, 54px);
  height: auto;
  object-fit: contain;
  filter: grayscale(100%);
  transition: filter 0.35s ease;
}

.skills__item:hover .skills__icon {
  filter: grayscale(0%);
}

.skills__percent {
  font-family: var(--font-serif);
  font-size: clamp(1rem, 1.8vw, 1.4rem);
  font-weight: 400;
  color: var(--color-black);
  line-height: 1;
}

.skills__name {
  font-size: 0.55rem;
  font-weight: 700;
  letter-spacing: 0.1em;
  color: var(--color-gray-mid);
  text-transform: uppercase;
  text-align: center;
  line-height: 1.2;
  max-width: 80%;
}

@media (max-width: 640px) {
  .skills__grid {
    grid-template-columns: repeat(2, 1fr);
  }

  .skills__ring-wrap {
    width: 150px;
    height: 150px;
  }
}
</style>
