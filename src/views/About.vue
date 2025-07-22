<template>
  <div class="about-container">
    <div class="about-content">
      <div class="paragraph">
        <div>
          I’m Berkay Ersoy, a passionate Game Developer with expertise in game design, AI-driven mechanics, and performance optimization. With a degree in Computer Engineering, I specialize in Unity and C#, focusing on crafting engaging and polished gaming experiences.
        </div>
        Throughout my career, I have designed and implemented intelligent game systems, smooth animations, and advanced features such as hint systems, procedural shuffling algorithms, and game analytics. My experience extends to AI behavior, game optimization, and multiplayer mechanics, ensuring seamless and immersive gameplay.
        <div>
          I thrive in collaborative environments and continuously seek opportunities to push the boundaries of game design and technology. I am currently exploring new opportunities where I can apply my skills and passion for game development to create engaging and high-quality player experiences.
        </div>
        <div style="margin-top: 40px;">You can reach me at <a href="mailto:mberkayersoy@gmail.com">mberkayersoy@gmail.com</a> or <router-link to="/contact">through here</router-link>.</div>
      </div>
      <div class="photo">
        <img src="img/aboutmeavatar.png" alt="Avatar of Me" />
      </div>
    </div>
  </div>
</template>

<style scoped>
.about-container {
  width: 100%;
  margin-bottom: 0;
  padding: 24px;
  box-sizing: border-box;
}

.about-content {
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 32px;
}

.paragraph {
  max-width: 700px;
  margin-bottom: 20px;
  font-size: 1.1em;
}

.photo {
  display: flex;
  justify-content: center;
  align-items: center;
}
.photo img {
  border-radius: 50%;
  width: 320px;
  height: 320px;
  object-fit: cover;
  box-shadow: 0 4px 24px rgba(0,0,0,0.08);
  border: 4px solid var(--accent-color);
}

@media (min-width: 900px) {
  .about-container {
    padding: 48px 32px;
  }
  .about-content {
    flex-direction: row;
    align-items: flex-start;
    gap: 64px;
  }
  .paragraph {
    flex: 2;
    margin-bottom: 0;
  }
  .photo {
    flex: 1;
    justify-content: flex-end;
    align-items: flex-start;
  }
  .photo img {
    width: 420px;
    height: 420px;
  }
}
</style>