<template>
  <section class="promo center">
    <div class="promo-text">
      <h1 class="promo-text__heading">
        Welcome to our collection of premium watches
      </h1>
      <p class="promo-text__discript">
        Our watches are not just timepieces, but also an expression of your
        personality and lifestyle. From classic designs to modern ones, we have
        a watch to suit every taste and occasion.
      </p>
    </div>
    <div class="collection">
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
        <img width="676" src="../assets/img/Rectangle 1.png" alt="baner" />
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
  background: rgb(20, 20, 20);
  &-text {
    display: flex;
    justify-content: space-between;
    &__heading {
      color: var(--white);
      font-size: 60px;
      font-weight: 600;
      line-height: 62px;
    }
    &__discript {
      max-width: 300px;
      color: var(--white);
      font-size: 14px;
      font-weight: 300;
      line-height: 18px;
    }
  }
}
.collection {
  margin-top: 70px;
  display: flex;
  justify-content: space-between;
  align-items: flex-end;
}

.slider {
  display: flex;
  justify-content: center;
  max-width: 436px;
  max-height: 255px;
  background: var(--darkGreen);
  transition: transform 0.3s ease;
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
</style>
