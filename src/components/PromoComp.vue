<template>
  <section class="promo center">
    <div class="collection">
      <h1 class="promo-text__heading">
        Welcome to our collection of premium watches
      </h1>
      <p class="promo-text__discript">
        Our watches are not just timepieces, but also an expression of your
        personality and lifestyle. From classic designs to modern ones, we have
        a watch to suit every taste and occasion.
      </p>
      <div class="slider-container">
        <div class="slider">
          <img
            v-for="(slide, index) in slides"
            :key="index"
            :src="slide.imgSrc"
            :alt="'Slide ' + (index + 1)"
            class="slide"
            v-show="index === currentIndex"
          />
        </div>
        <button @click="prevSlide" class="arrow arrow-left">
          <svg
            width="8"
            height="14"
            viewBox="0 0 8 14"
            fill="none"
            xmlns="http://www.w3.org/2000/svg"
          >
            <path
              d="M7 13L1 7L7 1"
              stroke="white"
              stroke-linecap="round"
              stroke-linejoin="round"
            />
          </svg>
        </button>
        <button @click="nextSlide" class="arrow arrow-right">
          <svg
            width="8"
            height="14"
            viewBox="0 0 8 14"
            fill="none"
            xmlns="http://www.w3.org/2000/svg"
          >
            <path
              d="M1 13L7 7L1 1"
              stroke="white"
              stroke-linecap="round"
              stroke-linejoin="round"
            />
          </svg>
        </button>
      </div>
      <div class="banner">
        <img
          class="banner-img"
          width="676"
          src="../assets/img/Rectangle 1.png"
          alt="baner"
        />
      </div>
    </div>
  </section>
</template>

<script>
import { mapState } from "vuex";
export default {
  data() {
    return {
      currentIndex: 0,
      sliderWidth: 436,
      sliderHeight: 255,
    };
  },
  computed: {
    ...mapState(["slides"]),
  },
  methods: {
    prevSlide() {
      this.currentIndex =
        (this.currentIndex - 1 + this.slides.length) % this.slides.length;
    },
    nextSlide() {
      this.currentIndex = (this.currentIndex + 1) % this.slides.length;
    },
  },
};
</script>

<style lang="scss" scoped>
.promo {
  padding-bottom: 80px;
  background: rgb(20, 20, 20);
  &-text {
    &__heading {
      color: var(--white);
      // font-size: 60px;
      font-size: clamp(38px, 5vw, 60px);
      font-weight: 600;
      line-height: clamp(40px, 5vw, 62px);
      grid-column-start: 1;
      grid-column-end: span 2;
      margin-bottom: 40px;
    }
    &__discript {
      max-width: 300px;
      color: var(--white);
      font-size: 14px;
      font-weight: 300;
      line-height: 18px;
      grid-column-start: 3;
    }
  }
}
.collection {
  margin-top: 70px;
  display: grid;
  grid-template-columns: 1fr 1fr;
}
.slider-container {
  grid-column: 1/2;
  align-self: end;
}
.slider {
  max-width: 436px;
  display: flex;
  justify-content: center;
  width: 436px;
  max-height: 255px;
  background: var(--darkGreen);
  transition: transform 0.3s ease;
  margin-right: 64px;
}
.arrow {
  margin-top: 20px;
  background: rgb(29, 31, 31);
  border: 1px solid var(--white);
  border-radius: 8px;
  padding: 14px 17px;
  color: var(--white);
  &:hover {
    border: 1px solid rgba(255, 255, 255, 0.5);
    stroke-opacity: 0.5;
  }

  &-right {
    margin-left: 12px;
  }
}
.banner {
  width: 100%;
  grid-column: 2/4;
  grid-row: 2/3;
  &-img {
    width: 100%;
    height: auto;
  }
}

@media (max-width: 1000px) {
  .promo-text__heading {
    margin-bottom: 40px;
  }
  .slider-container {
    margin-bottom: 40px;
  }
  .slider {
    margin-right: 20px;
  }
  .collection {
    display: grid;
    grid-template-columns: 1fr 1fr;

    min-height: auto;
  }
  .promo-text__heading {
    margin-bottom: 60px;
    grid-column: 1/4;
  }
  .promo-text__discript {
    grid-row: 2/3;
    padding-top: 70px;
  }

  .banner {
    grid-row: 3/4;
    grid-column: 1/4;
  }
}
@media (max-width: 750px) {
  .slider {
    width: 90%;
  }
  .collection {
    grid-template-columns: 1fr;
  }
  .promo-text__discript {
    grid-row: 3/4;
    grid-column: 1/2;
    justify-self: end;
    padding-top: 0px;
    margin-bottom: 40px;
  }
  .banner {
    grid-row: 4/5;
  }
}
@media (max-width: 500px) {
  .slider {
    width: 75%;
  }
  .collection {
    margin-top: 0px;
  }
}
@media (max-width: 400px) {
  .banner-img {
    max-width: 92%;
    height: 410px;
    object-fit: cover;
  }
  .promo-text__discript {
    padding-right: 25px;
  }
}
</style>
