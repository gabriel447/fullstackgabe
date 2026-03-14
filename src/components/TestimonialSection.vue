<template>
  <section class="testimonial">
    <div class="testimonial__header">
      <span class="testimonial__label">WHAT THEY SAY</span>
      <h2 class="testimonial__title">Testimonial Client</h2>
    </div>

    <div class="testimonial__wrapper"
      @touchstart="onTouchStart"
      @touchend="onTouchEnd"
    >
      <transition name="fade" mode="out-in">
        <div :key="current" class="testimonial__slide">
          <div class="testimonial__quote-mark" aria-hidden="true">&ldquo;</div>
          <p class="testimonial__quote">{{ testimonials[current].quote }}</p>
          <div class="testimonial__author">
            <img :src="testimonials[current].photo" :alt="testimonials[current].name" class="testimonial__photo" />
            <div class="testimonial__author-info">
              <p class="testimonial__name">{{ testimonials[current].name }}</p>
              <p class="testimonial__role">{{ testimonials[current].role }}</p>
            </div>
          </div>
        </div>
      </transition>
    </div>

    <div class="testimonial__controls">
      <button class="testimonial__arrow" @click="prev" aria-label="Previous">
        <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.5" width="20" height="20">
          <path d="M15 18l-6-6 6-6" stroke-linecap="round" stroke-linejoin="round"/>
        </svg>
      </button>

      <div class="testimonial__dots">
        <button
          v-for="(_, i) in testimonials"
          :key="i"
          class="testimonial__dot"
          :class="{ 'testimonial__dot--active': i === current }"
          @click="current = i"
          :aria-label="`Testimonial ${i + 1}`"
        />
      </div>

      <button class="testimonial__arrow" @click="next" aria-label="Next">
        <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.5" width="20" height="20">
          <path d="M9 18l6-6-6-6" stroke-linecap="round" stroke-linejoin="round"/>
        </svg>
      </button>
    </div>
  </section>
</template>

<script setup>
import { ref } from 'vue'

const testimonials = [
  {
    name: 'Andre Pamungkas',
    role: 'CEO ANTM',
    photo: 'https://i.pravatar.cc/96?img=11',
    quote: 'Gabriel consistently delivered beyond expectations. His technical depth and ability to communicate complex solutions in simple terms made the entire project a success. I wouldn\'t hesitate to work with him again.',
  },
  {
    name: 'Jane Smith',
    role: 'CTO TechCorp',
    photo: 'https://i.pravatar.cc/96?img=47',
    quote: 'Working with Gabriel was an incredible experience. His attention to detail and technical expertise helped us launch our product on time and within budget. A truly exceptional developer.',
  },
  {
    name: 'Marcus Reynolds',
    role: 'Product Manager · Startify',
    photo: 'https://i.pravatar.cc/96?img=52',
    quote: 'Gabriel brought both technical excellence and creative thinking to our team. He proactively identified bottlenecks in our codebase and proposed clean, scalable solutions. The kind of developer every team needs.',
  },
  {
    name: 'Sofia Mendes',
    role: 'Founder · Designova',
    photo: 'https://i.pravatar.cc/96?img=23',
    quote: 'What impressed me most about Gabriel was his ability to translate design concepts into pixel-perfect interfaces without losing any of the intended feel. Reliable, fast, and always open to feedback.',
  },
]

const current = ref(0)
let touchStartX = 0

function prev() {
  current.value = (current.value - 1 + testimonials.length) % testimonials.length
}

function next() {
  current.value = (current.value + 1) % testimonials.length
}

function onTouchStart(e) {
  touchStartX = e.touches[0].clientX
}

function onTouchEnd(e) {
  const diff = touchStartX - e.changedTouches[0].clientX
  if (Math.abs(diff) > 40) diff > 0 ? next() : prev()
}
</script>

<style scoped>
.testimonial {
  padding: 8rem 5% 7rem;
  border-top: 1px solid var(--color-gray);
}

.testimonial__header {
  text-align: center;
  margin-bottom: 5rem;
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 0.8rem;
}

.testimonial__label {
  font-size: 0.65rem;
  font-weight: 700;
  letter-spacing: 0.2em;
  color: var(--color-gray-mid);
}

.testimonial__title {
  font-family: var(--font-serif);
  font-size: clamp(2.2rem, 4vw, 3.2rem);
  font-weight: 400;
}

.testimonial__wrapper {
  max-width: 800px;
  margin: 0 auto;
}

.testimonial__slide {
  background: var(--color-white);
  border-radius: 16px;
  padding: 2.5rem;
  display: flex;
  flex-direction: column;
  gap: 1.2rem;
  box-shadow: 0 4px 24px rgba(0, 0, 0, 0.07);
}

.testimonial__quote-mark {
  font-family: var(--font-serif);
  font-size: 5rem;
  line-height: 0.7;
  color: var(--color-gray);
  user-select: none;
}

.testimonial__quote {
  font-family: var(--font-serif);
  font-size: clamp(0.95rem, 1.6vw, 1.1rem);
  line-height: 1.85;
  color: var(--color-gray-dark);
}

.testimonial__author {
  display: flex;
  align-items: center;
  gap: 0.9rem;
  padding-top: 0.8rem;
  border-top: 1px solid #f0f0f0;
}

.testimonial__photo {
  width: 48px;
  height: 48px;
  border-radius: 50%;
  object-fit: cover;
  flex-shrink: 0;
}

.testimonial__author-info {
  display: flex;
  flex-direction: column;
  gap: 0.15rem;
}

.testimonial__name {
  font-weight: 700;
  font-size: 0.9rem;
}

.testimonial__role {
  font-size: 0.7rem;
  letter-spacing: 0.08em;
  color: var(--color-gray-mid);
  text-transform: uppercase;
}

.testimonial__controls {
  display: flex;
  align-items: center;
  justify-content: center;
  gap: 1.5rem;
  margin-top: 2rem;
}

.testimonial__arrow {
  background: var(--color-white);
  border: 1px solid var(--color-gray);
  border-radius: 50%;
  width: 40px;
  height: 40px;
  display: flex;
  align-items: center;
  justify-content: center;
  cursor: pointer;
  color: var(--color-gray-dark);
  transition: background 0.2s, color 0.2s, border-color 0.2s;
  flex-shrink: 0;
}

.testimonial__arrow:hover {
  background: var(--color-black);
  color: var(--color-white);
  border-color: var(--color-black);
}

.testimonial__dots {
  display: flex;
  gap: 0.5rem;
  align-items: center;
}

.testimonial__dot {
  width: 7px;
  height: 7px;
  border-radius: 50%;
  background: var(--color-gray);
  border: none;
  cursor: pointer;
  transition: background 0.2s, transform 0.2s;
}

.testimonial__dot--active {
  background: var(--color-black);
  transform: scale(1.3);
}

.fade-enter-active,
.fade-leave-active {
  transition: opacity 0.35s ease;
}
.fade-enter-from,
.fade-leave-to {
  opacity: 0;
}

@media (max-width: 600px) {
  .testimonial__slide {
    padding: 2rem 1.6rem;
  }

  .testimonial__quote {
    font-size: 1rem;
    line-height: 1.9;
  }
}
</style>
