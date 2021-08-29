<template>
  <div class="my-hero">
    <div class="text-frame">
      <h1 class="typewriter">
        <span class="box"></span>
        <span class="hi">I am </span>
        <span class="text"></span>
        <span class="cursor">_</span>
      </h1>
    </div>
    <div class="hero-bg-overlay"></div>
  </div>
</template>

<script>
export default {
  mounted() {
    const words = [
      'Artyom Kouznetsov',
      'a Web Developer',
      'working with Wordpress',
      'working with VueJS / Nuxt',
      'a Photography Enthusiast',
      'Happy to meet you !',
    ]

    let cursor = gsap.to('.cursor', {
      opacity: 0,
      ease: 'power2.inOut',
      repeat: -1,
    })

    let boxTl = gsap.timeline()
    boxTl
      .to('.box', {
        duration: 1,
        width: '10vw',
        delay: 0.5,
        ease: 'power4.inOut',
      })
      .from('.hi', {
        duration: 1,
        y: '7vw',
        ease: 'power3.out',
        onComplete: () => {masterTl.play()}
      })
      .to('.box', {
        duration: 1,
        height: '7vw',
        ease: 'elastic.out',
      })

    let masterTl = gsap.timeline({
      repeat: -1,
    }).pause()

    words.forEach((word) => {
      let tlWord = gsap.timeline({
        repeat: 1,
        yoyo: true,
        repeatDelay: 1
      })
      tlWord.to('.text', {
        duration: 1,
        text: word,
      })
      masterTl.add(tlWord)
    })

  },
}
</script>

<style lang="scss" scoped>
.my-hero {
  position: relative;
  height: calc(100vh - 60px);
  width: 100%;
  background: url('/images/developer.jpg');
  background-position: bottom;
  background-size: cover;
  background-repeat: no-repeat;
  background-attachment: fixed;
}

.text-frame {
  position: absolute;
  display: flex;
  align-items: center;
  min-height: 100%;
}

.typewriter {
  position: relative;
  color: white;
  font-size: 5vw;
  font-weight: bold;
  padding-left: 15vw;
  overflow: hidden;

  .box {
    position: absolute;
    bottom: 0;
    display: inline-block;
    background-color: var(--hero-iam-color);
    height: 1vw;
  }

  .hi {
    display: inline-block;
  }

  .hi, .text {
    position: relative;
    z-index: 2;
  }
}

.hero-bg-overlay {
  background-color: rgba(0, 34, 104, 0.65);
  width: 100%;
  height: 100%;
}
</style>