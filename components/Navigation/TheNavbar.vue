<template>
  <div class="navbar-container">
    <header class="the-navbar">
      <div class="logo">
        <nuxt-link to="/"
          ><span class="logo-pt-1">ARTYOM</span>
          <span class="logo-pt-2">&lt;&sol;&gt;</span>
          <span class="logo-pt-3">DEV</span></nuxt-link
        >
      </div>
      <div class="spacer"></div>
      <div class="navigation-items">
        <ul class="nav-list">
          <li class="nav-item"><a href="#sec-about">About</a></li>
          <li class="nav-item"><a href="#sec-skills">Skills</a></li>
          <li class="nav-item"><a href="#sec-portfolio">Portfolio</a></li>
          <li class="nav-item"><a href="#sec-contact">Contact</a></li>
        </ul>
      </div>
      <TheSideNavToggle @toggle="$emit('sidenavToggle')" />
    </header>
  </div>
</template>

<script>
import TheSideNavToggle from '@/components/Navigation/TheSideNavToggle'

export default {
  name: 'TheNavbar',
  components: {
    TheSideNavToggle,
  },
  // mounted() {
  //   const theNavbar = document.querySelector('.the-navbar');
  //   gsap.timeline({
  //     scrollTrigger: {
  //       trigger: '.navbar-container',
  //       start: 'top 0%',
  //       onEnter: () => {
  //         theNavbar.classList.add('navbar-fixed');
  //       },
  //       onLeaveBack: () => {
  //         theNavbar.classList.remove('navbar-fixed');
  //       },
  //     }
  //   });
  // }
}
</script>


<style scoped lang="scss">

.navbar-container {
  height: 60px;
  // position: relative;
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  z-index: 950;
  // overflow-x:hidden; // removes horizontal scrolling created by ScrollTrigger :)
}

// .navbar-fixed {
//   position:fixed;
//   top: 0;
//   left: 0;
//   z-index: 200;
// }

.the-navbar {
  width: 100%;
  /* position: fixed; */
  height: 60px;
  display: flex;
  justify-content: space-around;
  align-items: center;
  background-color: var(--navbar-bg-color);
  z-index: 100;
  box-sizing: border-box;
  padding: 0 20px;
}

.logo, .nav-item {
  letter-spacing: .5px;
}

.logo {
  margin: 0 10px;
  font-size: 1.3rem;

  a {
    text-decoration: none;
    color: var(--nav-logo-color);
  }
  .logo-pt-1 {
    color: var(--nav-logo-color-1);
  }
  .logo-pt-2 {
    color: var(--nav-logo-color-2);
  }
  .logo-pt-3 {
    color: var(--nav-logo-color-3);
  }
}

.spacer {
  flex: 1;
}

.navigation-items {
  display: none;
}

@media (min-width: 768px) {
  .navigation-items {
    display: block;
  }
}

.nav-list {
  list-style: none;
  padding: 0;
  margin: 0;
  display: flex;
}

.nav-item {
  margin: 0 10px;
  position: relative;

  a {
    text-decoration: none;
    color: var(--nav-link-color);
    text-transform: uppercase;
    transition: color 0.3s;
    padding: 5px;
    line-height: 28px;

    &:hover {
      color: var(--nav-link-hover-color);
    }

    // Underline and overline
    &::before,
    &::after {
      content: '';
      position: absolute;
      top: 0em;
      bottom: 0em;
      left: 0em;
      right: 0em;
    }

    &::before {
      transform: scale(0, 1); // x is at 0%, y is at 100%
      transition: transform ease-out 250ms;
      border-top: 1px solid var(--nav-link-topline-hover-color);
      border-bottom: 1px solid var(--nav-link-bottomline-hover-color);
    }

    &:hover::before {
      transform: scale(1.05, 1);
    }
  }
}

/* .nav-item a:active,
.nav-item a.nuxt-link-active {
  color: white;
} */
</style>
