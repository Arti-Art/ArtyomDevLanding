<template>
  <footer>
    <div id="sec-contact" class="footer-content">

      <h2 class="footer-title"><slot /></h2>

      <div class="footer-line">
        <a :href=" 'mailto:' + myEmail"
          ><i class="fas fa-envelope"></i> {{ myEmail }}
          <i class="fas fa-envelope"></i
        ></a>
      </div>

      <div class="footer-line">
        <a :href=" 'https://www.instagram.com/' + instagram + '/' "
          ><i class="fab fa-instagram"></i> Instagram: @{{ instagram }} <i class="fab fa-instagram"></i></a>
      </div>

      <div class="footer-line">
        <div><i class="fab fa-discord"></i> Discord: {{ discord }} <i class="fab fa-discord"></i></div>
      </div>

      <div class="footer-line">
        <a :href="github"
          ><i class="fab fa-github"></i> My GitHub <i class="fab fa-github"></i></a>
      </div>

      <div class="copyrights">
        <p>Website created with Vue.JS, Nuxt and GSAP</p>
        <p>© 2021 - Artjom Kouznetsov / London UK / All rights reserved</p>
      </div>

    </div>

  </footer>
</template>

<script>
export default {
  name: 'TheFooter',
  props: {
    myEmail: {
      type: String,
      default: ''
    },
    instagram: {
      type: String,
      default: ''
    },
    discord: {
      type: String,
      default: ''
    },
    github: {
      type: String,
      default: ''
    },
  }
}
</script>

<style lang="scss" scoped>

.footer-content {
  display: flex;
  flex-direction: column;
  align-items: center;
  background: var(--footer-bg-color);
  color: var(--footer-text-color);
  padding: 45px 10px 15px;
  letter-spacing: 1px;
}

.footer-title {
  text-transform: uppercase;
  margin-bottom: 30px;
  letter-spacing: 4px;
  padding: 0px 10px;
  color: var(--footer-title-color);
  background-color: var(--footer-title-highlight-color);
}

.footer-line {
  min-height: 30px;
  transition: font-size .5s;
  & > * {
    cursor: pointer;
  }
  &:hover {
    font-size: large;
    color: var(--footer-text-hover-color);
  }
}

.copyrights {
  color: var(--footer-copyrights-color);
  text-align: center;
  margin-top: 20px;
  font-size: 11px;
}

</style>