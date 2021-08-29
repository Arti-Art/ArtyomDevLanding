<template>
  <div class="default-layout">
    <MyHero />
    <TheNavbar @sidenavToggle="displaySidenav = !displaySidenav" />
    <TheSidenav :show="displaySidenav" @close="displaySidenav = false" />
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

  // COLORS
  --clr-dark-purple: #00014a;
  --clr-dark-purple-tr: hsla(239, 100%, 15%, 0.8);
  --clr-dark-blue: #011129;
  --clr-light-orange: #ffca3d;
  --clr-orange: #f59300;
  --clr-pinkred: #ff2f5f;

  // ELEMENTS COLORS
  --navbar-bg-color: var(--clr-dark-purple);
  --nav-logo-color-1: white;
  --nav-logo-color-2: var(--clr-pinkred);
  --nav-logo-color-3: var(--clr-light-orange);
  // --nav-logo-color: var(--clr-light-orange);
  --nav-hamburger-color: white;
  --nav-link-color: white;
  --nav-link-hover-color: var(--clr-light-orange);
  --nav-link-topline-hover-color: var(--clr-light-orange);
  --nav-link-bottomline-hover-color: var(--clr-light-orange);
  // SIDENAV
  --nav-sidenav-color: var(--clr-dark-blue);
  --nav-sidenav-backdrop-color: #00030ce6;
  --nav-sidenav-border-color: var(--clr-pinkred);
  // HERO
  --hero-iam-color: var(--clr-pinkred);
  // FOOTER
  --footer-bg-color: var(--clr-dark-purple);
  --footer-highlight-color: var(--clr-orange);
  --footer-highlight-color2: var(--clr-light-orange);
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
