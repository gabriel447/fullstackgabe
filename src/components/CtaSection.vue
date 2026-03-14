<template>
  <section id="contact" class="cta">
    <span class="cta__brand">*FULLSTACKGABE ©</span>

    <div class="cta__content">
      <div class="cta__left">
        <span class="cta__label">LET'S WORK TOGETHER</span>
        <h2 class="cta__heading">
          Let's take our<br />
          relationship to<br />
          the next level
        </h2>
        <button class="cta__btn">
          Let's Talk
          <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" width="16" height="16">
            <path d="M7 17L17 7M17 7H7M17 7v10"/>
          </svg>
        </button>
      </div>

      <div class="cta__photo-wrap">
        <img :src="ctaPhoto" alt="Gabriel" class="cta__photo" />
      </div>

      <div class="cta__right">
        <p class="cta__quote">
          &ldquo; I build software that<br />
          makes a difference. &rdquo;
        </p>
        <div class="cta__contact-links">
          <a href="mailto:fullstackgabe@gmail.com" class="cta__contact-link">fullstackgabe@gmail.com</a>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
import ctaPhoto from '../assets/handsome-man-on-street-of-city.jpg'
</script>

<style scoped>
.cta {
  background: var(--color-black);
  color: var(--color-white);
  padding: 6rem 5%;
  position: relative;
}

.cta__brand {
  position: absolute;
  top: 2rem;
  right: 5%;
  font-size: 0.7rem;
  letter-spacing: 0.1em;
  font-weight: 600;
  color: rgba(255, 255, 255, 0.3);
}

.cta__content {
  display: grid;
  grid-template-columns: minmax(0, 1.4fr) 280px minmax(0, 1fr);
  align-items: center;
  gap: 4rem;
  max-width: 1200px;
  margin: 0 auto;
  padding-top: 2.5rem;
}

.cta__left {
  display: flex;
  flex-direction: column;
  gap: 2rem;
}

.cta__label {
  font-size: 0.6rem;
  font-weight: 700;
  letter-spacing: 0.2em;
  color: rgba(255, 255, 255, 0.4);
}

.cta__heading {
  font-family: var(--font-serif);
  font-size: clamp(2rem, 3.5vw, 3.5rem);
  font-weight: 400;
  line-height: 1.15;
}

.cta__btn {
  display: inline-flex;
  align-items: center;
  gap: 0.6rem;
  padding: 1rem 2rem;
  border-radius: 999px;
  border: 1.5px solid var(--color-white);
  color: var(--color-white);
  font-size: 0.85rem;
  font-weight: 600;
  letter-spacing: 0.04em;
  transition: background 0.25s, color 0.25s;
  width: fit-content;
}

.cta__btn:hover {
  background: var(--color-white);
  color: var(--color-black);
}

.cta__photo-wrap {
  width: 280px;
  height: 280px;
  border-radius: 50%;
  overflow: hidden;
  flex-shrink: 0;
  border: 1px solid rgba(255, 255, 255, 0.1);
}

.cta__photo {
  width: 100%;
  height: 100%;
  object-fit: cover;
  transition: transform 0.6s ease;
}

.cta__photo-wrap:hover .cta__photo {
  transform: scale(1.05);
}

.cta__right {
  display: flex;
  flex-direction: column;
  gap: 2rem;
  align-items: flex-end;
  justify-content: flex-end;
}

.cta__quote {
  font-family: var(--font-serif);
  font-size: clamp(1rem, 1.8vw, 1.25rem);
  line-height: 1.7;
  color: rgba(255, 255, 255, 0.7);
  text-align: right;
}

.cta__contact-links {
  display: flex;
  flex-direction: column;
  gap: 0.4rem;
  text-align: right;
}

.cta__contact-link {
  font-size: 0.8rem;
  color: rgba(255, 255, 255, 0.4);
  text-decoration: none;
  transition: color 0.2s;
  letter-spacing: 0.02em;
}

.cta__contact-link:hover {
  color: rgba(255, 255, 255, 0.9);
}

@media (max-width: 900px) {
  .cta__content {
    grid-template-columns: 1fr;
    text-align: center;
    justify-items: center;
    gap: 3rem;
  }

  .cta__left {
    align-items: center;
    order: 2;
  }

  .cta__photo-wrap {
    order: 1;
    width: 240px;
    height: 240px;
  }

  .cta__heading {
    font-size: 2.6rem;
  }

  .cta__quote {
    font-size: 1.1rem;
  }

  .cta__contact-link {
    font-size: 0.9rem;
  }

  .cta__right {
    order: 3;
    align-items: center;
  }

  .cta__quote {
    text-align: center;
  }

  .cta__contact-links {
    text-align: center;
    align-items: center;
  }
}
</style>
