<template>
  <section id="method" class="method">
    <div class="method__header">
      <span class="method__label">HOW I WORK</span>
      <h2 class="method__title">My Method</h2>
    </div>

    <div class="method__grid">
      <div class="method__card">
        <div class="method__img-wrap">
          <img :src="empathyPhoto" alt="Empathy phase" class="method__img" />
        </div>
        <h3 class="method__phase">Phase 1: Empathy</h3>
        <p class="method__text">
          This is the <strong>discovery phase</strong>. My goal is to fully understand the user's world.
          I conduct research, observe people, and engage in conversations to gain deep insights into
          their needs, motivations, and pain points. I'm not trying to solve the problem yet, but to
          truly feel and understand it from their perspective.
        </p>
      </div>

      <div class="method__card">
        <h3 class="method__phase">Phase 2: Ideation</h3>
        <p class="method__text">
          This is the <strong>creation phase</strong>. Once I have a clear understanding of the user,
          I use those insights to brainstorm a wide range of potential solutions. My focus is on
          quantity over quality, generating as many ideas as possible—even the wild or seemingly
          unfeasible ones. This is where I connect the user's needs with innovative possibilities.
        </p>
        <div class="method__img-wrap">
          <img :src="ideationPhoto" alt="Ideation phase" class="method__img" />
        </div>
      </div>

      <div class="method__card">
        <div class="method__img-wrap">
          <img :src="experimentPhoto" alt="Experimentation phase" class="method__img" />
        </div>
        <h3 class="method__phase">Phase 3: Experimentation</h3>
        <p class="method__text">
          This is the <strong>validation phase</strong>. I take the best ideas from the ideation phase
          and turn them into tangible prototypes. These can be simple sketches, mock-ups, or even
          role-playing scenarios. My purpose is not to create a finished product but to test my
          assumptions and get feedback from users quickly.
        </p>
      </div>
    </div>
  </section>
</template>

<script setup>
import empathyPhoto from '../assets/mock-up-poster-frame-in-modern-interior-background.jpg'
import ideationPhoto from '../assets/business-people-using-a-tablet-e1660837616242.jpg'
import experimentPhoto from '../assets/business-team-working-colleagues-successful-concept.jpg'
</script>

<style scoped>
.method {
  padding: 8rem 5% 7rem;
  border-top: 1px solid var(--color-gray);
}

.method__header {
  text-align: center;
  margin-bottom: 5rem;
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 0.8rem;
}

.method__label {
  font-size: 0.65rem;
  font-weight: 700;
  letter-spacing: 0.2em;
  color: var(--color-gray-mid);
}

.method__title {
  font-family: var(--font-serif);
  font-size: clamp(2.2rem, 4vw, 3.2rem);
  font-weight: 400;
}

.method__grid {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 3rem;
  align-items: start;
}

.method__card {
  display: flex;
  flex-direction: column;
  gap: 1.2rem;
}

.method__img-wrap {
  border-radius: 8px;
  overflow: hidden;
  aspect-ratio: 4/3;
}

.method__img {
  width: 100%;
  height: 100%;
  object-fit: cover;
  filter: grayscale(15%);
  transition: filter 0.4s, transform 0.5s ease;
}

.method__card:hover .method__img {
  filter: grayscale(0%);
  transform: scale(1.05);
}

.method__phase {
  font-family: var(--font-serif);
  font-size: 1.6rem;
  font-weight: 400;
  color: var(--color-black);
  line-height: 1.2;
}

.method__text {
  font-size: 0.875rem;
  line-height: 1.85;
  color: var(--color-gray-dark);
}

.method__text strong {
  color: var(--color-black);
}

@media (max-width: 900px) {
  .method__grid {
    grid-template-columns: 1fr;
    max-width: 560px;
    margin: 0 auto;
  }

  .method__card .method__phase { order: 2; }
  .method__card .method__text  { order: 3; }
  .method__card .method__img   { order: 1; }
}
</style>
