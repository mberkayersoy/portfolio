<template>
  <div class="contact-container">
    <h1>Let's get in touch</h1>
    <div class="contact-desc">I'm looking for a job!<br/>Feel free to contact me about any opportunity, or just to chat about coding, games, music or anything else.</div>
    <ul>
      <li>
        <i class="fa fa-envelope-o fa-lg fa-fw"></i>
        <a href="mailto:mberkayersoy@gmail.com" target="_blank">mberkayersoy@gmail.com</a>
      </li>
      <li>
        <i class="fa fa-linkedin fa-lg fa-fw" style="vertical-align: -5%;"></i>
        <a href="https://www.linkedin.com/in/berkay-ersoy-291869228/" target="_blank">linkedin.com/berkay-ersoy</a>
      </li>
      <li>
        <i class="fa fa-github fa-lg fa-fw"></i>
        <a href="https://github.com/mberkayersoy" target="_blank">github.com/mberkayersoy</a>
      </li>
      <li>
        <i class="fa fa-gamepad fa-lg fa-fw"></i>
        <a href="https://mberkayersoy.itch.io" target="_blank">mberkayersoy.itch.io</a>
      </li>
    </ul>
  </div>
</template>

<style scoped>
ul {
  list-style: none;
  padding-inline-start: 0px;
}

li {
    line-height: 1.8em;
    font-size: 1.2em;
  }

.contact-container {
  width: 100%;
  padding: 24px;
  box-sizing: border-box;
}
@media (min-width: 900px) {
  .contact-container {
    padding: 48px 32px;
  }
}
.contact-desc {
  margin-bottom: 32px;
  font-size: 1.1em;
}

@media only screen and (min-width: 620px){
  ul {
    padding-inline-start: 40px;
  }

  li {
    line-height: 2em;
    font-size: 1.4em;
  }
}

i {
  margin-right: 20px;
}
</style>
