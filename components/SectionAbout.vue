<template>
  <section id="sec-about" class="sec-about">
    <div class="sec-about-cont">
      <h2 class="sec-about-cont-title">Hi ! I'm Arti</h2>
      <p class="sec-about-cont-text">
        I started web development over a year ago at <a href="https://becode.org/" target="_blank">becode.org</a> in Liège &lpar;Belgium&rpar; as a new challenge.
        I am now looking for a job opportunity in London in a fun and dynamic environment. I'm into Javascript frameworks, WordPress and photography.
        If you would like to know more about me, <a href="#sec-contact">get in touch !</a>
      </p>
    </div>
    <nuxt-img
      src="/images/artisquare.jpg"
      alt=""
      sizes="xl:2000px lg:1000px md:600px sm:400px xs:300px"
      class="sec-about-img"
    />
    <!-- <div class="about-overlay"></div> -->
  </section>
</template>

<script>
export default {
  mounted() {
    const tlAbout = gsap.timeline({
      scrollTrigger: {
        trigger: '.sec-about',
        start: 'top 85%',
        end: 'bottom bottom',
        scrub: 1,
      },
    })

    tlAbout
      .from('.sec-about-img', {
        yPercent: 15,
        scale: 1.25,
        opacity: 0,
        duration: 1,
      })

      const tlAboutText = gsap.timeline({
        scrollTrigger: {
          trigger: '.sec-about',
          start: 'top 50%',
          end: 'bottom bottom',
        },
      })
      tlAboutText
        .from(
          '.sec-about-cont-title',
          {
            x: 300,
            opacity: 0,
            duration: 0.5,
          },
          '+=0'
        )

  },
}
</script>

<style lang="scss" scoped>
.sec-about {
  width: 100%;
  height: 100vh;
  min-height: 640px;
  text-align: left;
  background: rgb(0, 0, 0);
  color: white;
  position: relative;
  overflow: hidden;
}

.sec-about-cont {
  padding: clamp(3em, 10vw, 9em) clamp(1em, 10vw, 5em);
  z-index: 1;
  position: absolute;
  bottom: 50px;

  .sec-about-cont-title, .sec-about-cont-text {
    background: var(--about-text-bg);
    border-radius: 5px;
  }

  .sec-about-cont-title {
    font-size: clamp(38px, 6vw, 70px);
    display: inline-block;
    padding: 0px 20px;
    margin-bottom: 20px;
  }

  .sec-about-cont-text {
    font-family: 'Poppins', sans-serif;
    font-size: clamp(18px, 3vw, 24px);
    letter-spacing: .5px;
    padding: 10px 20px;
    max-width: 600px;

    a {
      color: var(--about-text-accent);
    }
  }
}

.sec-about-img {
  width: 100%;
  height: 100vh;
  position: absolute;
  object-fit: cover;
  top: 0;
}

// .about-overlay {
//   position: absolute;
//   width: 100%;
//   height: 100%;
//   top: 0;
//   left: 0;
//   background: var(--about-bg-grad);
// }

</style>