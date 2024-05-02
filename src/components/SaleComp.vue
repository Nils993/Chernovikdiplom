<template>
  <section id="sale" class="sale center">
    <h2 class="sale__title">Sale</h2>
    <div class="sale-content">
      <div class="sale-imglist">
        <img
          class="sale-imglist__item"
          @click="selectImg(item)"
          v-for="item in listImg"
          :key="item.id"
          :src="item"
          alt=""
        />
      </div>
      <img class="sale__bigimg" :src="bigImg" alt="" />
      <div class="sale-discription">
        <h3 class="sale-discription__name">
          Greenlane Watch By Police For MenHT
        </h3>
        <p class="sale-discription__tag">Product tag: PEWJK2227003</p>
        <div class="sale-discription__price">
          <span>€700</span>
          <span class="sale-discription__price-discont"
            ><strike>€1000</strike></span
          >
        </div>

        <hr />
        <h4 class="sale-discription__title">Description</h4>
        <p class="sale-discription__info">
          Richly detailed with an&nbsp;understated design&nbsp;&mdash; the
          Police Men&rsquo;s Greenlane watch features a&nbsp;versatile
          multifunction design that fits effortlessly into work and play. The
          steel case is&nbsp;adorned with a semi-&nbsp;transparent black dial.
          The timepiece exhibits a&nbsp;contrast through a&nbsp;black&nbsp;IP
          bracelet with matching crown and pushers.
        </p>
        <hr />
        <h4 class="sale-discription__title">DETAILS & FEATUREStion</h4>
        <div class="sale-discription__info">
          <p>Gender: man Size: 46x54.5mm</p>
          <p>Case Colour: Steel</p>
          <p>Band Material: Metal</p>
          <p>Case Material: Metal</p>
          <p>Features: Multifunction</p>
          <p>Water Resistant: 5 (ATM)</p>
          <p>Band Colour: Steel</p>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  data() {
    return {
      bigImg: require("../assets/img/img63.png"),
      listImg: {
        img1: require("../assets/img/img63.png"),
        img2: require("../assets/img/img64.png"),
        img3: require("../assets/img/img65.png"),
        img4: require("../assets/img/img66.png"),
      },
    };
  },
  methods: {
    selectImg(item) {
      this.bigImg = item;
    },
  },
};
</script>

<style lang="scss" scoped>
.sale {
  padding-top: 80px;
  padding-bottom: 160px;
  &__title {
    color: var(--darkGreen);
    font-size: clamp(32px, 5vw, 40px);
    line-height: clamp(40px, 5vw, 44px);
    font-weight: 600;
  }
  &-content {
    margin-top: 80px;
    display: grid;
    grid-template-columns: 146px 406px 430px;
    justify-content: center;
  }
  &-imglist {
    display: grid;
    grid-template-rows: repeat(4, auto);
    gap: 10px;

    &__item {
      height: auto;
      background: var(--colorText);
      max-width: 100%;
    }
  }
  &__bigimg {
    margin-left: 10px;
    object-fit: cover;
    background: var(--colorText);
    max-width: 100%;
    height: 100%;
  }
  &-discription {
    margin-left: 50px;
    &__name {
      color: var(--colorText);
      font-size: clamp(24px, 5vw, 38px);
      line-height: clamp(24px, 5vw, 40px);
      font-weight: 400;
    }
    &__tag {
      color: var(--colorText);
      opacity: 0.5;
      font-family: Epilogue;
      font-size: 14px;
      font-weight: 400;
      line-height: 18px;
      margin-top: 8px;
      margin-bottom: 16px;
    }
    &__price {
      font-size: 18px;
      font-weight: 400;
      line-height: 24px;
      color: var(--colorText);
      margin-bottom: 40px;
      &-discont {
        margin-left: 10px;
        opacity: 0.5;
      }
    }
    &__title {
      color: var(--colorText);
      font-size: 18px;
      font-weight: 500;
      line-height: 24px;
      text-transform: uppercase;
      margin-top: 8px;
      margin-bottom: 16px;
    }
    &__info {
      color: var(--colorText);
      font-size: 14px;
      font-weight: 400;
      line-height: 18px;
      opacity: 0.5;
      margin-bottom: 20px;
    }
  }
}
@media (max-width: 1000px) {
  .sale-content {
    display: grid;
    grid-template-columns: 146px 406px;
    grid-template-rows: auto auto; /* Добавляем автоматическую высоту для последнего блока */
    justify-content: center;
    height: auto; /* Убираем фиксированную высоту */
  }
  .sale-discription {
    grid-column: span 2;
    margin-top: 40px;
    margin-left: 0px;
  }
}
@media (max-width: 600px) {
  .sale-content {
    grid-template-columns: 80px 245px;
  }
  .sale__bigimg {
    max-width: 100%;
  }
}
</style>
