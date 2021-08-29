<template>
  <section id="sec-skills" class="sec-skills">

    <div class="sec-skills-cont">
      <h2>Technical skills</h2>
      <div class="skills-grid">
        <div class="cell"><p>Vue.js &amp; Nuxt</p></div>
        <div class="cell"><p>WordPress</p></div>
        <div class="cell"><p>Javascript</p></div>
        <div class="cell"><p>Shopify &amp; Liquid</p></div>
        <div class="cell"><p>React.Js</p></div>
        <div class="cell"><p>CSS &amp; Sass</p></div>
      </div>

      <h2>Other skills</h2>
      <div class="skills-grid-2">
        <div class="cell"><p>Fluency in French, English, Russian</p></div>
        <div class="cell"><p>Photography</p></div>
        <div class="cell"><p>Gardening</p></div>
      </div>

      <!-- <h3>Download Resume / CV</h3> -->
    </div>

  </section>
</template>

<style lang="scss" scoped>
.sec-skills {
  width: 100%;
  padding: 7em 0;
  font-family: 'Poppins';
  background: rgb(0, 0, 0);
  color: rgb(0, 0, 0);
  background: url('/images/whitewallsmall.jpg');
  background-repeat: no-repeat;
  background-size: cover;
  position: relative;
}

.sec-skills-cont {
  max-width: 600px;
  margin: 0 auto;
  text-align: center;

  h2 {
    display: inline-block;
    background-color: rgb(0, 0, 0);
    padding: 0px 8px;
    margin-bottom: 15px;
    border-radius: 2px;
    color: white;
    font-size: 1.7rem;
    text-transform: uppercase;
  }

  p {
    font-size: 1.3rem;
    background: hsla(0, 0%, 100%, 0.5);
    display: inline-block;
    padding: 0px 8px;
    border-radius: 2px;
    box-shadow: rgb(0 0 0 / 25%) 1.5px 1.5px 1.5px;
    &:hover {
      background: hsla(0, 0%, 100%, 0.877);
    }
  }

  .skills-grid {
    margin-bottom: 40px;
  }

  .cell {
    width: 100%;
    margin-bottom: 10px;
  }

  .skills-grid .cell {
    position: relative;
  }

}

@media (min-width: 768px) {
  .skills-grid {
    display: grid;
    grid-template-columns: 1fr 1fr;
    row-gap: 10px;
    .cell {
      text-align: left;
      margin-bottom: 0;
    }
    .cell:nth-child(odd) p {
      position: absolute;
      top: 0;
      right: 10px;
    }
  }
}

</style>