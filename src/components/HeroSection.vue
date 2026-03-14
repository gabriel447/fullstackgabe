<template>
  <section id="hero" class="hero">
    <div class="hero__main">
      <div class="hero__left">
        <h1 class="hero__title">Fullstack<br />Developer</h1>
        <div class="hero__wave" aria-hidden="true">
          <svg viewBox="0 0 300 20" preserveAspectRatio="none" xmlns="http://www.w3.org/2000/svg">
            <polyline
              points="0,10 10,2 20,18 30,2 40,18 50,2 60,18 70,2 80,18 90,2 100,18 110,2 120,18 130,2 140,18 150,2 160,18 170,2 180,18 190,2 200,18 210,2 220,18 230,2 240,18 250,2 260,18 270,2 280,18 290,2 300,10"
              fill="none" stroke="#111" stroke-width="1.5" />
          </svg>
        </div>
        <div class="hero__stats">
          <div class="hero__stat">
            <span class="hero__stat-num">7</span>
            <span class="hero__stat-label">YEARS OF<br />EXPERIENCE</span>
          </div>
          <div class="hero__stat-sep"></div>
          <div class="hero__stat">
            <span class="hero__stat-num">60</span>
            <span class="hero__stat-label">PROJECTS<br />DONE</span>
          </div>
        </div>
      </div>

      <div class="hero__center">
        <div class="hero__photo-wrap">
          <img :src="profilePhoto" alt="Gabriel" class="hero__photo" />
        </div>
      </div>

      <div class="hero__right">
        <span class="hero__asterisk">*</span>
        <p class="hero__bio">
          I'm Gabriel, a Full-stack Developer<br />
          based in Brazil, focused on creating<br />
          software solutions.
        </p>
        <div class="hero__socials">
          <a href="https://github.com" target="_blank" class="hero__social" aria-label="GitHub">
            <svg viewBox="0 0 24 24" fill="currentColor" width="20" height="20">
              <path
                d="M12 2C6.477 2 2 6.477 2 12c0 4.418 2.865 8.166 6.839 9.489.5.092.682-.217.682-.482 0-.237-.008-.866-.013-1.7-2.782.603-3.369-1.34-3.369-1.34-.454-1.156-1.11-1.463-1.11-1.463-.908-.62.069-.608.069-.608 1.003.07 1.531 1.03 1.531 1.03.892 1.529 2.341 1.087 2.91.832.092-.647.35-1.088.636-1.338-2.22-.253-4.555-1.11-4.555-4.943 0-1.091.39-1.984 1.029-2.683-.103-.253-.446-1.27.098-2.647 0 0 .84-.268 2.75 1.026A9.578 9.578 0 0 1 12 6.836a9.59 9.59 0 0 1 2.504.337c1.909-1.294 2.747-1.026 2.747-1.026.546 1.377.202 2.394.1 2.647.64.699 1.028 1.592 1.028 2.683 0 3.842-2.339 4.687-4.566 4.935.359.309.678.919.678 1.852 0 1.336-.012 2.415-.012 2.743 0 .267.18.578.688.48C19.138 20.163 22 16.418 22 12c0-5.523-4.477-10-10-10z" />
            </svg>
          </a>
          <a href="https://linkedin.com" target="_blank" class="hero__social" aria-label="LinkedIn">
            <svg viewBox="0 0 24 24" fill="currentColor" width="20" height="20">
              <path
                d="M20.447 20.452h-3.554v-5.569c0-1.328-.027-3.037-1.852-3.037-1.853 0-2.136 1.445-2.136 2.939v5.667H9.351V9h3.414v1.561h.046c.477-.9 1.637-1.85 3.37-1.85 3.601 0 4.267 2.37 4.267 5.455v6.286zM5.337 7.433a2.062 2.062 0 0 1-2.063-2.065 2.064 2.064 0 1 1 2.063 2.065zm1.782 13.019H3.555V9h3.564v11.452zM22.225 0H1.771C.792 0 0 .774 0 1.729v20.542C0 23.227.792 24 1.771 24h20.451C23.2 24 24 23.227 24 22.271V1.729C24 .774 23.2 0 22.222 0h.003z" />
            </svg>
          </a>
          <a href="https://instagram.com" target="_blank" class="hero__social" aria-label="Instagram">
            <svg viewBox="0 0 24 24" fill="currentColor" width="20" height="20">
              <path
                d="M12 2.163c3.204 0 3.584.012 4.85.07 3.252.148 4.771 1.691 4.919 4.919.058 1.265.069 1.645.069 4.849 0 3.205-.012 3.584-.069 4.849-.149 3.225-1.664 4.771-4.919 4.919-1.266.058-1.644.07-4.85.07-3.204 0-3.584-.012-4.849-.07-3.26-.149-4.771-1.699-4.919-4.92-.058-1.265-.07-1.644-.07-4.849 0-3.204.013-3.583.07-4.849.149-3.227 1.664-4.771 4.919-4.919 1.266-.057 1.645-.069 4.849-.069zm0-2.163c-3.259 0-3.667.014-4.947.072-4.358.2-6.78 2.618-6.98 6.98-.059 1.281-.073 1.689-.073 4.948 0 3.259.014 3.668.072 4.948.2 4.358 2.618 6.78 6.98 6.98 1.281.058 1.689.072 4.948.072 3.259 0 3.668-.014 4.948-.072 4.354-.2 6.782-2.618 6.979-6.98.059-1.28.073-1.689.073-4.948 0-3.259-.014-3.667-.072-4.947-.196-4.354-2.617-6.78-6.979-6.98-1.281-.059-1.69-.073-4.949-.073zm0 5.838a6.162 6.162 0 1 0 0 12.324 6.162 6.162 0 0 0 0-12.324zM12 16a4 4 0 1 1 0-8 4 4 0 0 1 0 8zm6.406-11.845a1.44 1.44 0 1 0 0 2.881 1.44 1.44 0 0 0 0-2.881z" />
            </svg>
          </a>
        </div>
      </div>
    </div>

    <div class="hero__tags">
      <span class="hero__tag hero__tag--asterisk">
        <svg viewBox="0 0 24 24" width="18" height="18" fill="none" stroke="currentColor" stroke-width="2.2"
          stroke-linecap="round" aria-hidden="true">
          <line x1="12" y1="2" x2="12" y2="22" />
          <line x1="2" y1="7" x2="22" y2="17" />
          <line x1="2" y1="17" x2="22" y2="7" />
        </svg>
      </span>
      <span class="hero__tag hero__tag--red">FRONT-END</span>
      <span class="hero__tag hero__tag--black">BACK-END</span>
      <span class="hero__tag hero__tag--yellow">MOBILE</span>
      <span class="hero__tag hero__tag--light">DATABASE</span>
      <span class="hero__tag hero__tag--purple">AI</span>
    </div>

  </section>
</template>

<script setup>
import profilePhoto from '../assets/54693114.jpeg'
</script>

<style scoped>
.hero {
  padding: 5rem 8% 4rem;
  display: flex;
  flex-direction: column;
  gap: 3rem;
  max-width: 1400px;
  margin: 0 auto;
  width: 100%;
}

.hero__main {
  display: grid;
  grid-template-columns: 1fr auto 1fr;
  align-items: center;
  gap: 3rem;
}

.hero__left {
  display: flex;
  flex-direction: column;
  gap: 2rem;
}

.hero__title {
  font-family: var(--font-serif);
  font-size: clamp(1.8rem, 3.2vw, 3rem);
  font-weight: 400;
  line-height: 1.1;
  letter-spacing: -0.02em;
}

.hero__wave {
  display: flex;
  justify-content: flex-start;
}

.hero__wave svg {
  width: 260px;
  height: 16px;
  opacity: 0.55;
}

.hero__stats {
  display: flex;
  align-items: center;
  gap: 2rem;
}

.hero__stat {
  display: flex;
  flex-direction: column;
  align-items: flex-start;
  gap: 0.5rem;
}

.hero__stat-sep {
  width: 1px;
  height: 44px;
  background: var(--color-gray);
  flex-shrink: 0;
}

.hero__stat-num {
  font-family: var(--font-serif);
  font-size: clamp(1.8rem, 3.2vw, 2.8rem);
  font-weight: 400;
  line-height: 1;
  vertical-align: baseline;
}

.hero__stat-label {
  font-size: 0.6rem;
  font-weight: 600;
  letter-spacing: 0.07em;
  color: var(--color-gray-mid);
  text-transform: uppercase;
  line-height: 1.5;
}

.hero__center {
  display: flex;
  justify-content: center;
}

.hero__photo-wrap {
  width: clamp(220px, 26vw, 340px);
  height: clamp(220px, 26vw, 340px);
  border-radius: 50%;
  overflow: hidden;
  flex-shrink: 0;
  box-shadow: 0 20px 60px rgba(0, 0, 0, 0.12);
}

.hero__photo {
  width: 100%;
  height: 100%;
  object-fit: cover;
  transition: transform 0.6s ease;
}

.hero__photo-wrap:hover .hero__photo {
  transform: scale(1.04);
}

.hero__right {
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 1.5rem;
  text-align: center;
}

.hero__asterisk {
  font-size: 3.5rem;
  font-weight: 200;
  line-height: 1;
  color: var(--color-gray-mid);
}

.hero__bio {
  font-family: var(--font-serif);
  font-size: clamp(0.95rem, 1.5vw, 1.15rem);
  line-height: 1.8;
  color: var(--color-gray-dark);
}

.hero__socials {
  display: flex;
  gap: 1rem;
  justify-content: center;
}

.hero__social {
  color: var(--color-gray-mid);
  transition: color 0.2s;
  display: flex;
  align-items: center;
  padding: 0.4rem;
}

.hero__social:hover {
  color: var(--color-black);
}

.hero__tags {
  display: flex;
  flex-wrap: wrap;
  gap: 0.6rem;
  align-items: center;
  justify-content: center;
  padding-top: 2rem;
}

.hero__tag {
  padding: 0.65rem 1.5rem;
  border-radius: 999px;
  font-size: 0.8rem;
  font-weight: 700;
  letter-spacing: 0.06em;
  cursor: default;
  transition: transform 0.15s;
}

.hero__tag:hover {
  transform: translateY(-1px);
}

.hero__tag--asterisk {
  background: var(--color-black);
  color: var(--color-white);
  width: 46px;
  height: 46px;
  padding: 0;
  display: inline-flex;
  align-items: center;
  justify-content: center;
  flex-shrink: 0;
}

.hero__tag--red {
  background: var(--color-red);
  color: white;
}

.hero__tag--black {
  background: var(--color-black);
  color: white;
}

.hero__tag--yellow {
  background: var(--color-yellow);
  color: var(--color-black);
}

.hero__tag--light {
  background: var(--color-gray);
  color: var(--color-black);
}

.hero__tag--purple {
  background: var(--color-purple);
  color: white;
}


@media (max-width: 900px) {
  .hero__main {
    grid-template-columns: 1fr;
    justify-items: center;
    text-align: center;
    gap: 2.5rem;
  }

  .hero__left {
    align-items: center;
    order: 2;
    width: 100%;
  }

  .hero__center {
    order: 1;
  }

  .hero__right {
    order: 3;
  }

  .hero__wave {
    justify-content: center;
  }

  .hero__stats {
    justify-content: center;
  }

  .hero__stat {
    align-items: center;
  }

  .hero__tags {
    justify-content: center;
  }
}

@media (max-width: 480px) {
  .hero {
    padding: 3rem 5% 2.5rem;
    gap: 3rem;
  }

  .hero__photo-wrap {
    width: 260px;
    height: 260px;
  }

  .hero__title {
    font-size: 2.8rem;
  }

  .hero__stat-num {
    font-size: 2.6rem;
  }

  .hero__stat-label {
    font-size: 0.7rem;
  }

  .hero__bio {
    font-size: 1.1rem;
    line-height: 1.9;
  }

  .hero__wave svg {
    width: 100%;
    max-width: 320px;
  }
}
</style>
