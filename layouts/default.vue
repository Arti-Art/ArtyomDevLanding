<template>
  <div class="default-layout">
    <TheSidenav :show="displaySidenav" @close="displaySidenav = false" />
    <TheNavbar @sidenavToggle="displaySidenav = !displaySidenav" />
    <MyHero />
    <Nuxt />
    <TheFooter
      my-email="art.kouznetsov@gmail.com"
      instagram="von_kouznetsoff"
      discord="Arti-Art#2960"
      github="https://github.com/Arti-Art"
      >Contact Me</TheFooter
    >
  </div>
</template>

<script>
import MyHero from '~/components/MyHero.vue'
import TheNavbar from '~/components/Navigation/TheNavbar.vue'
import TheSidenav from '~/components/Navigation/TheSidenav.vue'
import TheFooter from '~/components/TheFooter.vue'
export default {
  components: {
    MyHero,
    TheNavbar,
    TheSidenav,
    TheFooter,
  },
  data() {
    return {
      displaySidenav: false,
    }
  },
}
</script>

<style lang="scss">
/* For unscoped application-wide styles, write css/sass here :) */

:root {
  // FONTS
  --ff-title: 'Nunito';
  // --ff-title: 'Poppins';
  --ff-body: 'Open Sans';

  // COLORS - DELETE
  --clr-dark-purple: #00014a;
  --clr-dark-purple-tr: hsla(239, 100%, 15%, 0.8);
  --clr-dark-blue: #011129;
  --clr-light-orange: #ffca3d;
  --clr-orange: #f59300;
  --clr-pinkred: #ff2f5f;

  // COLORS V2
  --smoky-black: #12130fff;
  --smoky-black-alpha: rgba(18, 19, 15, 0.9);
  --cultured: #eff1edff;
  --cultured-alpha: rgba(239, 241, 237, 0.97);
  --green-cyan: #2d936cff;
  --dark-spring-green: #297045ff;
  --rose-madder: #e71d36ff;
  --sizzling-red: #ff5a5fff;
  --copper-rose: #986c6aff;
  --cornflower-blue: #7796cbff;

  // NAVBAR
  --navbar-bg-color: var(--cultured-alpha);
  --nav-logo-color-1: var(--smoky-black);
  --nav-logo-color-2: var(--clr-pinkred);
  --nav-logo-color-3: var(--sizzling-red);
  --nav-hamburger-color: var(--smoky-black);
  --nav-link-color: var(--smoky-black);
  --nav-link-hover-color: var(--sizzling-red);
  --nav-link-topline-hover-color: var(--sizzling-red);
  --nav-link-bottomline-hover-color: var(--sizzling-red);
  // SIDENAV
  --sidenav-bg-clr: var(--cultured);
  --sidenav-link-color: var(--smoky-black);
  --sidenav-backdrop-clr: var(--smoky-black-alpha);
  --nav-sidenav-border-color: var(--sizzling-red);
  // HERO
  --hero-iam-color: var(--clr-pinkred);
  // ABOUT
  --about-bg-col: var(--cultured);
  --about-text-clr: var(--cultured);
  --about-text-bg: var(--smoky-black);
  --about-text-accent: var(--sizzling-red);
  --about-bg-grad: linear-gradient(0deg, rgb(0, 0, 0) 1%, rgba(255,255,255,0) 50%);
  // SKILLS
  --skils-title-bg-clr: var(--smoky-black);
  --skils-title-clr: var(--cultured);
  --skils-text-clr: var(--smoky-black);
  // PORTFOLIO
  --portfo-bg-clr: var(--smoky-black);
  --portfo-title-bg-clr: var(--cultured);
  --portfo-title-clr: var(--smoky-black);
  --portfo-text-clr: var(--cultured);
  // FOOTER
  --footer-bg-color: var(--cultured);
  --footer-title-color: var(--cultured);
  --footer-title-highlight-color: var(--smoky-black);
  --footer-text-color: var(--smoky-black);
  --footer-text-hover-color: var(--sizzling-red);
  --footer-copyrights-color: var(--copper-rose);
}

html {
  scroll-behavior: smooth;
  font-family: var(--ff-body), sans-serif;
}

body {
  overflow-x: hidden;
}

h1,
h2,
h3,
h4,
h5,
h6 {
  font-family: var(--ff-title), sans-serif;
}

.default-layout {
  position: relative;
}

.intro {
  font-family: 'Poppins', sans-serif;
  font-size: 25px;
  text-transform: uppercase;
  line-height: 1.75;
  color: rgb(204, 51, 17);
  margin: 15px 0;

  .navlink:hover {
    color: rgb(110, 26, 8);
  }

  .nuxt-link-exact-active {
    border-bottom: 2px solid rgb(204, 51, 17);
  }

  position: relative;
  display: inline-block;
  // << inline-block so that ::b&a match the width of the text block. Set to block to make ::b&a span full width.
  &::before,
  &::after {
    content: ''; // set to empty. If no content property, ::before & ::after won't work
    display: block;
    position: absolute;
  }

  &::before {
    background: white;
    z-index: -1;
    height: 101%;
    left: -20px;
    right: -20px;
  }

  &::after {
    background: rgb(255, 108, 108);
    // width: 100%; // will stop at the edge of my text block if block is inline-block
    width: 100vw;
    left: 50%;
    top: 0;
    transform: translateX(-50%);
    z-index: -2;
    height: 100%;
  }
}
</style>
