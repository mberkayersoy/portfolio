<template>
  <div class="contact">
    <h1>Get in touch</h1>
    <p class="intro">
      I'm open to new opportunities — feel free to reach out about a role,
      a project, or just to talk games, music or code.
    </p>

    <ul class="links">
      <li>
        <span class="link-label"><i class="fa fa-envelope-o"></i> Email</span>
        <a href="mailto:mberkayersoy@gmail.com">mberkayersoy@gmail.com</a>
      </li>
      <li>
        <span class="link-label"><i class="fa fa-linkedin"></i> LinkedIn</span>
        <a href="https://www.linkedin.com/in/berkay-ersoy-291869228/" target="_blank" rel="noopener">
          linkedin.com/in/berkay-ersoy
        </a>
      </li>
      <li>
        <span class="link-label"><i class="fa fa-github"></i> GitHub</span>
        <a href="https://github.com/mberkayersoy" target="_blank" rel="noopener">
          github.com/mberkayersoy
        </a>
      </li>
      <li>
        <span class="link-label"><i class="fa fa-gamepad"></i> itch.io</span>
        <a href="https://mberkayersoy.itch.io" target="_blank" rel="noopener">
          mberkayersoy.itch.io
        </a>
      </li>
    </ul>
  </div>
</template>

<style scoped>
.contact {
  max-width: 520px;
}

h1 { margin-bottom: 16px; }

.intro {
  font-size: 0.95rem;
  color: var(--text-muted);
  margin-bottom: 48px;
  line-height: 1.7;
}

.links {
  list-style: none;
  padding: 0;
  margin: 0;
  display: flex;
  flex-direction: column;
  gap: 0;
}

.links li {
  display: flex;
  align-items: baseline;
  gap: 24px;
  padding: 18px 0;
  border-bottom: 1px solid var(--border);
  margin: 0;

  &:first-child { border-top: 1px solid var(--border); }
}

.link-label {
  font-size: 0.72rem;
  letter-spacing: 0.08em;
  text-transform: uppercase;
  color: var(--text-muted);
  min-width: 84px;
  flex-shrink: 0;
}

.links a {
  font-size: 0.9rem;
  color: var(--text);
  text-decoration: none;
  transition: opacity 0.15s;
  &:hover { opacity: 0.7; }
}
</style>
