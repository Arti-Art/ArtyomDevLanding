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
    <!-- <div class="scroll-down"><a href="#sec-about"><p>Scroll Down</p></a></div> -->
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

    gsap.to('.cursor', {
      opacity: 0,
      ease: 'power2.inOut',
      repeat: -1,
    })

    const boxTl = gsap.timeline()
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

    const masterTl = gsap.timeline({
      repeat: -1,
    }).pause()

    words.forEach((word) => {
      const tlWord = gsap.timeline({
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
  // background-color: rgba(0, 34, 104, 0.65);
  background: url('/BlackFade.png');
  background-position: center bottom;
  background-size: cover;
  width: 100%;
  height: 100%;
}

// .scroll-down {
//   position: fixed;
//   bottom: 120px;
//   width: 100%;
//   a {
//     cursor: pointer;
//   }
//   p {
//     font-family: 'Nunito';
//     text-align: center;
//     color: white;
//     font-size: 22px;
//     text-transform: uppercase;
//     animation: scrolldown 2s infinite alternate;
//   }
// }

// @keyframes scrolldown {
//   0% {
//     opacity: 0.9;
//     transform: translateY(0px);
//   }
//   100% {
//     opacity: 0.2;
//     transform: translateY(-20px);
//   }
// }
</style>