<template>
  <div
    class="drawer-toggle"
    role="button"
    @click="$emit('toggle')">
    <div class="bar"></div>
    <div class="bar"></div>
    <div class="bar"></div>
  </div>
</template>

<style scoped lang="scss">

.drawer-toggle {
  display: flex;
  flex-direction: column;
  justify-content: space-around;
  height: 50%;
  width: 35px;
  cursor: pointer;

  .bar {
    width: 90%;
    height: 2px;
    background-color: var(--nav-hamburger-color);
  }

  &:hover {
    animation-name: size_pulse;
    animation-duration: 1s;
    animation-iteration-count: infinite;
    animation-direction: alternate;
  }

}

@keyframes size_pulse {
	from { transform: scale(1); }
	to { transform: scale(1.15); }
}

@media (min-width: 768px) {
  .drawer-toggle {
    display: none;
  }
}

</style>
