<template>
<div class="sidenav-container">
  <div
    v-if="show"
    class="sidenav-backdrop"
    @click="$emit('close')"></div>
  <div name="old-nuxt-transition slide-side">
    <div
      v-if="show"
      class="sidenav">
      <ul
        class="nav-list"
        @click="$emit('close')">
        <li class="nav-item"><a href="#sec-about">About</a></li>
        <li class="nav-item"><a href="#sec-skills">Skills</a></li>
        <li class="nav-item"><a href="#sec-portfolio">Portfolio</a></li>
        <li class="nav-item"><a href="#sec-contact">Contact</a></li>
      </ul>
    </div>
  </div>
</div>
</template>

<script>
export default {
  name: "TheSidenav",
  props: {
    show: {
      type: Boolean,
      default: false
    }
  }
};
</script>


<style scoped lang="scss">
.sidenav-container {
  height: 100%;
  width: 100%;
}

.sidenav-backdrop {
  width: 100%;
  height: 100%;
  background-color: var(--nav-sidenav-backdrop-color);
  z-index: 1000;
  position: fixed;
  top: 0;
  left: 0;
}

.sidenav {
  height: 100%;
  width: 300px;
  background-color: var(--nav-sidenav-color);
  z-index: 10000;
  position: fixed;
  top: 0;
  left: 0;
  box-sizing: border-box;
  padding: 30px;
  &::after {
    content: '';
    position: absolute;
    top: 0em;
    bottom: 0em;
    left: 100%;
    right: 0em;
    // transform: scale(0, 1); // x is at 0%, y is at 100%
    // transition: transform ease-out 250ms;
    border-right: 50px solid var(--nav-sidenav-border-color);
  }
}

.slide-side-enter-active,
.slide-side-leave-active {
  transition: all 0.3s ease-out;
}
.slide-side-enter,
.slide-side-leave-to {
  transform: translateX(-100%);
}

.nav-list {
  list-style: none;
  padding: 0;
  margin: 0;
}

.nav-item {
  margin: 20px 0;
  position: relative;
  a {
    text-decoration: none;
    color: var(--nav-link-color);
    font-size: 1.5rem;
    text-transform: uppercase;
    transition: color 0.3s;
    display: block;
    text-align: left;
    margin-left: 2rem;
    letter-spacing: 2px;

    &::before {
      content: '';
      position: absolute;
      top: 0em;
      bottom: 0em;
      left: 0em;
      right: 0em;
    }

    &::before {
      transform: scale(0, 1); // x is at 0%, y is at 100%
      transition: transform ease-out 500ms;
      border-bottom: 2px solid var(--nav-link-bottomline-hover-color);
    }

    &:hover::before {
      transform: scale(1, 1);
      transform-origin: left;
    }
  }
}

.nav-item a:hover {
  color: var(--nav-link-hover-color);
}
</style>
