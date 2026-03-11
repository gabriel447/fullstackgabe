<template>
  <section id="experience" class="experience">
    <div class="experience__header">
      <span class="experience__label">BACKGROUND</span>
      <h2 class="experience__title">Education &amp; Experience</h2>
    </div>

    <div class="experience__body">

      <div class="experience__group">
        <h3 class="experience__group-title">
          <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.5" width="14" height="14" stroke-linecap="round" stroke-linejoin="round">
            <rect x="2" y="7" width="20" height="14" rx="2"/><path d="M16 7V5a2 2 0 0 0-2-2h-4a2 2 0 0 0-2 2v2"/>
          </svg>
          Experience
        </h3>
        <div class="experience__timeline">
          <div v-for="(item, index) in workItems" :key="index" class="experience__item">
            <div class="experience__dot-col">
              <div class="experience__dot"></div>
            </div>
            <div class="experience__content">
              <span class="experience__role">{{ item.role }}</span>
              <span class="experience__company">{{ item.company }}</span>
            </div>
            <span class="experience__badge">{{ item.year }}</span>
          </div>
        </div>
      </div>

      <div class="experience__group">
        <h3 class="experience__group-title">
          <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.5" width="14" height="14" stroke-linecap="round" stroke-linejoin="round">
            <path d="M22 10v6M2 10l10-5 10 5-10 5z"/><path d="M6 12v5c3 3 9 3 12 0v-5"/>
          </svg>
          Education
        </h3>
        <div class="experience__timeline">
          <div v-for="(item, index) in eduItems" :key="index" class="experience__item">
            <div class="experience__dot-col">
              <div class="experience__dot"></div>
            </div>
            <div class="experience__content">
              <span class="experience__role">{{ item.role }}</span>
              <span class="experience__company">{{ item.company }}</span>
            </div>
            <span class="experience__badge">{{ item.year }}</span>
          </div>
        </div>
      </div>

    </div>
  </section>
</template>

<script setup>
const workItems = [
  { year: '2024 – 2025', role: 'Fullstack Developer', company: 'Novagne' },
  { year: '2023 – 2024', role: 'IT Support Specialist', company: 'Novagne' },
]

const eduItems = [
  { year: '2020 – 2022', role: 'Software Development', company: 'Positive University' },
]
</script>

<style scoped>
.experience {
  padding: 8rem 5% 7rem;
  border-top: 1px solid var(--color-gray);
}

.experience__header {
  text-align: center;
  margin-bottom: 5rem;
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 0.8rem;
}

.experience__label {
  font-size: 0.65rem;
  font-weight: 700;
  letter-spacing: 0.2em;
  color: var(--color-gray-mid);
}

.experience__title {
  font-family: var(--font-serif);
  font-size: clamp(2.2rem, 4vw, 3.2rem);
  font-weight: 400;
}

.experience__body {
  max-width: 720px;
  margin: 0 auto;
  display: flex;
  flex-direction: column;
  gap: 3rem;
}

.experience__group-title {
  font-size: 0.65rem;
  font-weight: 700;
  letter-spacing: 0.18em;
  text-transform: uppercase;
  color: var(--color-gray-mid);
  margin-bottom: 0.6rem;
  display: flex;
  align-items: center;
  gap: 0.45rem;
}

.experience__timeline {
  position: relative;
  padding-left: 0;
}

.experience__timeline::before {
  content: '';
  position: absolute;
  left: 9px;
  top: 16px;
  bottom: 16px;
  width: 1px;
  background: var(--color-gray);
  z-index: 0;
}

.experience__item {
  display: flex;
  align-items: center;
  gap: 1.2rem;
  padding: 1rem 0;
  border-bottom: 1px solid #f0f0f0;
}

.experience__item:last-child {
  border-bottom: none;
}

.experience__dot-col {
  width: 20px;
  flex-shrink: 0;
  display: flex;
  justify-content: center;
  position: relative;
  z-index: 1;
}

.experience__dot {
  width: 9px;
  height: 9px;
  border-radius: 50%;
  background: var(--color-white);
  border: 1.5px solid var(--color-gray);
  transition: border-color 0.2s, background 0.2s;
}

.experience__item:hover .experience__dot {
  border-color: var(--color-black);
  background: var(--color-black);
}

.experience__content {
  flex: 1;
  display: flex;
  flex-direction: column;
  gap: 0.15rem;
  min-width: 0;
}

.experience__role {
  font-family: var(--font-serif);
  font-size: 1rem;
  font-weight: 400;
  color: var(--color-black);
  line-height: 1.2;
}

.experience__company {
  font-size: 0.65rem;
  font-weight: 700;
  letter-spacing: 0.1em;
  text-transform: uppercase;
  color: var(--color-gray-mid);
}

.experience__badge {
  font-size: 0.68rem;
  font-weight: 500;
  color: var(--color-gray-mid);
  letter-spacing: 0.04em;
  padding: 0.28rem 0.8rem;
  border: 1px solid var(--color-gray);
  border-radius: 999px;
  white-space: nowrap;
  flex-shrink: 0;
}

@media (max-width: 600px) {
  .experience__badge {
    display: none;
  }
}
</style>
