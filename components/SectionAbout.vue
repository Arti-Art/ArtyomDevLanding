<template>
  <section class="sec-about" id="sec-about">
    <div class="sec-about-cont">
      <h2 class="sec-about-cont-title">Hi ! I'm Arti</h2>
      <p class="sec-about-cont-text">
        I started web development over a year ago at <a href="https://becode.org/" target="_blank">becode.org</a> in Liège &lpar;Belgium&rpar; as a new challenge.
        I am now looking for a job opportunity in London in a fun and dynamic environment. I'm into Javascript frameworks, WordPress and photography.
        If you would like to know more about me, <a href="#sec-contact">get in touch !</a>
      </p>
    </div>
    <!-- <img src="~/assets/images/main-page-background.jpg" alt="">
    <img src="/images/photographer01.jpg" alt=""> -->
    <nuxt-img
      src="/images/artisquare.jpg"
      alt=""
      sizes="xl:2000px lg:1000px md:600px sm:400px xs:300px"
      class="sec-about-img"
    />
    <div class="about-overlay"></div>
  </section>
</template>

<script>
export default {
  mounted() {
    let tlAbout = gsap.timeline({
      scrollTrigger: {
        trigger: '.sec-about',
        start: 'top 90%',
        end: 'bottom bottom',
        scrub: 1,
      },
    })

    tlAbout
      .from('.sec-about-img', {
        yPercent: -20,
        scale: 1.3,
        opacity: 0,
        duration: 1,
      })

      let tlAboutText = gsap.timeline({
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
    background: var(--clr-dark-purple-tr);
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
      color: var(--clr-pinkred);
    }
  }
}

.sec-about-img {
  width: 100%;
  height: 100vh;
  position: absolute;
  object-fit: cover;
  // right: 0;
  top: 0;
}

.about-overlay {
  position: absolute;
  width: 100%;
  height: 100%;
  top: 0;
  left: 0;
  // background-color: rgba(0, 0, 0, 0.102);
  background: linear-gradient(0deg, rgba(0,1,74,1) 1%, rgba(255,255,255,0) 50%);
}
</style>