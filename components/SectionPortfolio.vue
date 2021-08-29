<template>
  <section
    id="sec-portfolio"
    class="sec-portfolio"
  >
    <div v-if="modalIsOpen" class="img-modal">
      <div @click="prevImg" class="left-arrow">&#5176;</div>
      <div @click="nextImg" class="right-arrow">&#5171;</div>
      <div @click="closeModal" class="img-modal-container">
        <img :src="imagePath" alt="Gallery image">
      </div>
    </div>

    <div class="sec-portfolio-title-box"><h2 class="sec-portfolio-title">Portfolio</h2></div>
    <p class="sec-portfolio-description">Work in progress - at the moment, only featuring some of my photographic works.</p>

    <div class="sec-portfolio-gallery">
      <template v-for="num in 7">
        <div @click="openModal(num)" :class="`gallery-img img${num}`" :key="num">
          <div><p>View Fullscreen</p></div>
        </div>
      </template>
    </div>
    
  </section>
</template>

<script>
export default {
  data() {
    return {
      modalIsOpen: false,
      currentImgIndex: 1,
      currentImgPath: ''
    }
  },
  computed: {
    imagePath() { return `/gallery/Img${this.currentImgIndex}.jpg`}
  },
  methods: {
    openModal(index) {
      this.currentImgIndex = index
      this.modalIsOpen = true
    },
    closeModal() {
      this.modalIsOpen = false
    },
    prevImg() {
      if (this.currentImgIndex == 1) {
        this.currentImgIndex = 15
      } else {
        this.currentImgIndex--
      }
    },
    nextImg() {
      if (this.currentImgIndex == 15) {
        this.currentImgIndex = 1
      } else {
        this.currentImgIndex++
      }
    },
  },
  mounted() {
    console.log('Component Mounted')
  },
}
</script>

<style lang="scss" scoped>
.sec-portfolio {
  background-color: rgb(0, 0, 0);
  padding: 4em 0;
}

.sec-portfolio-title-box {
  margin: 0 auto;
  width: 166px;
  .sec-portfolio-title {
    display: inline-block;
    background-color: #ffffff;
    color: #000000;
    padding: 0px 8px;
    margin-bottom: 15px;
    border-radius: 2px;
    font-size: 1.7rem;
    text-transform: uppercase;
    text-align: center;
  }
}

.sec-portfolio-description {
  color: rgb(206, 206, 206);
  font-family: 'Poppins', sans-serif;
  text-align: center;
  margin-bottom: 60px;
}

.sec-portfolio-gallery {
  margin: 0 5vw;
  display: grid;
  grid-template-columns: 1fr 1fr;
  grid-template-rows: auto;
  gap: 10px;
  grid-template-areas:
    'img2 img2'
    'img1 img6'
    'img3 img5'
    'img4 img7';

  .gallery-img {
    width: 100%;
    height: 300px;
    background-repeat: no-repeat;
    background-size: cover;
    background-position: center;
    cursor: pointer;
  }
}

@media (min-width: 768px) {
  .sec-portfolio-gallery {
    grid-template-columns: 1fr 1fr 1fr 1fr;
    grid-template-areas:
      'img1 img6 img2 img2'
      'img3 img5 img4 img7';
  }
}

// Images
.img1 {
  grid-area: img1;
  background-image: url('/gallery/thumbs/Img1.jpg');
}
.img2 {
  grid-area: img2;
  background-image: url('/gallery/thumbs/Img2.jpg');
}
.img3 {
  grid-area: img3;
  background-image: url('/gallery/thumbs/Img3.jpg');
  // height: 610px !important;
  // 300px x2 +10px of central grid gap
}
.img4 {
  grid-area: img4;
  background-image: url('/gallery/thumbs/Img4.jpg');
}
.img5 {
  grid-area: img5;
  background-image: url('/gallery/thumbs/Img5.jpg');
}
.img6 {
  grid-area: img6;
  background-image: url('/gallery/thumbs/Img6.jpg');
}
.img7 {
  grid-area: img7;
  background-image: url('/gallery/thumbs/Img7.jpg');
}

// Gallery Image titles
.gallery-img div {
  width: 100%;
  height: 100%;
  background-color: rgb(0, 0, 0);
  opacity: 0;
  display: flex;
  justify-content: center;
  align-items: center;
  transition: all ease-in-out 200ms;

  &:hover {
    opacity: 0.8;
  }
}

.gallery-img p {
  font-family: 'Open Sans', sans-serif;
  font-size: 18px;
  color: white;
  text-decoration: none;
  text-transform: uppercase;
}

// Popup window when clicked
.img-modal {
  position: relative;
  width: 100vw;
  height: 100vh;
  background-color: rgba(0, 0, 0, 0.9);
  position: fixed;
  top: 0;
  left: 0;
  z-index: 100;

  .img-modal-container {
    width: 100%;
    height: 100%;
    display: flex;
    justify-content: center;
    align-items: center;
  }

  .left-arrow, .right-arrow {
    position: absolute;
    top: 48%;
    z-index: 150;
    width: 50px;
    height: 50px;
    border: 1px solid white;
    border-radius: 50%;
    color: rgb(255, 255, 255);
    font-size: 25px;
    background-color: rgba(0, 0, 0, 0.2);
    display: flex;
    justify-content: center;
    align-items: center;
    cursor: pointer;
  }

  .left-arrow {
    left: 10vw;
  }
  .right-arrow {
    right: 10vw;
  }

  img {
    max-height: 80vh;
    max-width: 80vw;
  }
}

</style>